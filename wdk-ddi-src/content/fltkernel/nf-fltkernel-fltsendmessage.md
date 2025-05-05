---
UID: NF:fltkernel.FltSendMessage
title: FltSendMessage function (fltkernel.h)
description: FltSendMessage sends a message to a waiting user-mode application on behalf of a minifilter driver or a minifilter driver instance.
tech.root: ifsk
ms.date: 05/02/2025
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Windows Server 2003 SP1, and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltSendMessage
 - fltkernel/FltSendMessage
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltSendMessage
---

# FltSendMessage function

## -description

**FltSendMessage** sends a message to a waiting user-mode application on behalf of a minifilter driver or a minifilter driver instance.

## -parameters

### -param Filter [in]

Opaque filter pointer for the caller. This parameter is required and can't be NULL.

### -param ClientPort [in]

Pointer to a variable that contains the opaque client port pointer for the connection port between the user-mode application and the kernel-mode minifilter driver. For more information about the client port pointer, see the description of the **ConnectNotifyCallback** parameter in the reference entry for [**FltCreateCommunicationPort**](nf-fltkernel-fltcreatecommunicationport.md).

### -param SenderBuffer [in]

Pointer to a minifilter-allocated buffer containing the message to send to the user-mode application. This parameter is required and can't be NULL.

### -param SenderBufferLength [in]

Size, in bytes, of the buffer that **SenderBuffer** points to. See **Remarks** for more information.

### -param ReplyBuffer [out, optional]

Pointer to a miniport-allocated buffer that receives a reply from the application, if any. This parameter is optional and can be NULL.

### -param ReplyLength [in, out]

Size, in bytes, of the buffer that **ReplyBuffer** points to. This parameter is optional, but must be non-NULL when **ReplyBuffer** isn't NULL.

### -param Timeout [in, optional]

A pointer to a timeout value that specifies the total absolute or relative length of time, in units of 100 nanoseconds, for which the caller (miniport) can be put into a wait state until the message is received by the user-mode application and until it receives a reply if a reply is expected.

A positive value specifies an absolute time, relative to January 1, 1601. A negative value specifies an interval relative to the current time. Set **Timeout** to NULL if the caller can be put into a wait state indefinitely.

## -returns

**FltSendMessage** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_BUFFER_OVERFLOW        | A miniport-allocated buffer wasn't large enough. This is an error code. |

| STATUS_INSUFFICIENT_RESOURCES | **FltSendMessage** encountered a pool allocation failure. This is an error code. |
| STATUS_PORT_DISCONNECTED      | The communication port has been disconnected. This is an error code. |
| STATUS_THREAD_IS_TERMINATING  | The wait was interrupted because the thread has been terminated by an application or user. |
| STATUS_TIMEOUT                | The **Timeout** interval expired before the message could be delivered or before a reply was received. This is a success code. |

## -remarks

**FltSendMessage** sends a message to a user-mode application on behalf of a minifilter driver or a minifilter driver instance.

If the application calls [**FilterGetMessage**](/windows/win32/api/fltuser/nf-fltuser-filtergetmessage) to get the message before the minifilter driver calls **FltSendMessage** to send it, the message that **SendBuffer** points to is delivered immediately when **FltSendMessage** is called. This is typically the case when the application calls **FilterGetMessage** from inside a message loop.

Otherwise, if an application has not called to get a message, *FltMgr* puts the minifilter into a wait state as follows:

* If **Timeout** points to a nonzero value and the application calls [**FilterGetMessage**](/windows/win32/api/fltuser/nf-fltuser-filtergetmessage) before the **Timeout** interval expires, the message is delivered.

* If **Timeout** points to a nonzero value and the application doesn't call **FilterGetMessage** before the **Timeout** interval expires, the message isn't delivered and **FltSendMessage** returns STATUS_TIMEOUT as a success code.

* If **Timeout** points to zero (```*Timeout == 0```), **FltSendMessage** returns without waiting.

* If **Timeout** is NULL (```Timeout == NULL```), the minifilter is put into a wait state indefinitely. When the application calls **FilterGetMessage**, the message is delivered.

After the message is delivered, if **ReplyBuffer** is NULL, **FltSendMessage** returns STATUS_SUCCESS.

Otherwise, if **ReplyBuffer** isn't NULL, the minifilter is put into a wait state as follows:

* If **Timeout** is nonzero and the application calls [**FilterReplyMessage**](/windows/win32/api/fltuser/nf-fltuser-filterreplymessage) before the **Timeout** interval expires, the minifilter receives the reply, and **FltSendMessage** returns STATUS_SUCCESS.

* If **Timeout** is nonzero and the minifilter doesn't receive a reply before the **Timeout** interval expires, **FltSendMessage** returns STATUS_TIMEOUT as a success code.

* If **Timeout** points to zero (```*Timeout == 0```), **FltSendMessage** returns without waiting.

* If **Timeout** is zero when the minifilter is waiting for the reply, the minifilter is put into a wait state indefinitely. When the application calls **FilterReplyMessage**, the minifilter receives the reply, and **FltSendMessage** returns STATUS_SUCCESS.

### Padding and Buffer Size

Problems can occur when the caller doesn't consider system-specific structure padding that might occur.

For example, say a minifilter declares the following structure in which to receive a reply, and passes a pointer to it in **ReplyBuffer**:

``` C
typedef struct _REPLY_STRUCT
{
    FILTER_REPLY_HEADER Header;
    REPLY_DATA Data;  // The structure to be sent to the minifilter with the reply.
} REPLY_STRUCT, *PREPLY_STRUCT;
```

Setting **ReplyLength** to ```sizeof(REPLY_STRUCT)``` would capture any padding that might be added to the end of any member of the structure, but isn't an accurate representation of the actual size of the structure and each of its members.

Setting **ReplyLength** to ```sizeof(FILTER_REPLY_HEADER) + sizeof(REPLY_DATA)``` ensures that any padding at the end of either structures is ignored. In the event that padding might be added after the **Header** structure, ```offsetof(REPLY_STRUCT, Data)``` can be used to accurately access the beginning of the **Data** structure, and ```sizeof(REPLY_DATA)``` can be used to determine the true number of bytes in the **Data** structure.

## -see-also

[**FilterGetMessage**](/windows/win32/api/fltuser/nf-fltuser-filtergetmessage)

[**FilterReplyMessage**](/windows/win32/api/fltuser/nf-fltuser-filterreplymessage)

[**FilterSendMessage**](/windows/win32/api/fltuser/nf-fltuser-filtersendmessage)

[**FltCreateCommunicationPort**](nf-fltkernel-fltcreatecommunicationport.md)
