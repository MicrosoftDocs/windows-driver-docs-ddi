---
UID: NC:fltkernel.PFLT_MESSAGE_NOTIFY
tech.root: ifsk
title: PFLT_MESSAGE_NOTIFY
ms.date: 07/10/2024
targetos: Windows
description: Learn more about the PFLT_MESSAGE_NOTIFY callback function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: FltMgr.sys
req.header: fltkernel.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: FltMgr.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - fltkernel.h
api_name:
 - PFLT_MESSAGE_NOTIFY
f1_keywords:
 - PFLT_MESSAGE_NOTIFY
 - fltkernel/PFLT_MESSAGE_NOTIFY
dev_langs:
 - c++
helpviewer_keywords:
 - PFLT_MESSAGE_NOTIFY
---

## -description

*FltMgr* calls a minifilter's **MessageNotifyCallback** callback function whenever a user-mode application calls [**FilterSendMessage**](/windows/win32/api/fltuser/nf-fltuser-filtersendmessage) to send a message to the minifilter through the client port.

## -parameters

### -param PortCookie

[in] Pointer to minifilter-defined information that uniquely identifies this client port. When the client port was created, the minifilter returned this context pointer in the **ConnectionPortCookie** parameter of its [**ConnectNotifyCallback**](nc-fltkernel-pflt_connect_notify.md) routine.

### -param InputBuffer

[in] Pointer to a caller-allocated buffer containing the message to be sent to the minifilter.

**InputBuffer** is a pointer to a raw, unlocked user-mode buffer. This pointer is valid only in the context of the user-mode process and must only be accessed from within a **try/except** block.

*FltMgr* calls [**ProbeForRead**](../wdm/nf-wdm-probeforread.md) to validate this pointer, but it doesn't ensure that the buffer is properly aligned. If the buffer contains structures that have alignment requirements, the minifilter is responsible for performing any necessary alignment checks. To do this, the minifilter can use the [**IS_ALIGNED**](/previous-versions/ff549486(v=vs.85)) macro as shown in the [MiniSpy](https://github.com/microsoft/windows-driver-samples/tree/main/filesys/miniFilter/minispy) sample minifilter.

This parameter is optional and can be NULL.

### -param InputBufferLength

[in] Size, in bytes, of the buffer that **InputBuffer** points to. This parameter is ignored if **InputBuffer** is NULL.

### -param OutputBuffer

[out] Pointer to a caller-allocated buffer that receives the reply, if any, from the minifilter.

**OutputBuffer** is a pointer to a raw, unlocked user-mode buffer. This pointer is valid only in the context of the user-mode process and must only be accessed from within a **try/except** block.

*FltMgr* calls [**ProbeForWrite**](../wdm/nf-wdm-probeforwrite.md) to validate this pointer, but it doesn't ensure that the buffer is properly aligned. If the buffer contains structures that have alignment requirements, the minifilter is responsible for performing any necessary alignment checks. To do this, the minifilter can use the [**IS_ALIGNED**](/previous-versions/ff549486(v=vs.85)) macro as shown in the [MiniSpy](https://github.com/microsoft/windows-driver-samples/tree/main/filesys/miniFilter/minispy) sample minifilter.

This parameter is optional and can be NULL.

### -param OutputBufferLength

[in] Size, in bytes, of the buffer that **OutputBuffer** points to. This parameter is ignored if **OutputBuffer** is NULL.

### -param ReturnOutputBufferLength

[out] Pointer to a caller-allocated variable that receives the number of bytes returned in the buffer that **OutputBuffer** points to.

## -returns

**MessageNotifyCallback** returns STATUS_SUCCESS if the operation succeeds. Otherwise, it returns an appropriate NTSTATUS value such as:

| Return code | Meaning |
| ----------- | ------- |
| STATUS_INSUFFICIENT_RESOURCES | There aren't enough resources to complete the operation. |
| STATUS_INVALID_PARAMETER | One or more of the input parameters are invalid. |

## -remarks

Minifilters can optionally implement **MessageNotifyCallback**. If a minifilter doesn't implement this callback, any request made from user mode to send data to the port will receive an error.

For more information, see [Communication between user-mode and minifilters](/windows-hardware/drivers/ifs/communication-between-user-mode-and-kernel-mode).

## -see-also

[**ConnectNotifyCallback**](nc-fltkernel-pflt_connect_notify.md)

[**FilterSendMessage**](/windows/win32/api/fltuser/nf-fltuser-filtersendmessage)

[**FltCreateCommunicationPort**](nf-fltkernel-fltcreatecommunicationport.md)
