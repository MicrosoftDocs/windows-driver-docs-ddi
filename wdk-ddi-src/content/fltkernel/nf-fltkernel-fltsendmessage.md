---
UID: NF:fltkernel.FltSendMessage
title: FltSendMessage function (fltkernel.h)
description: FltSendMessage sends a message to a waiting user-mode application on behalf of a minifilter driver or a minifilter driver instance.
old-location: ifsk\fltsendmessage.htm
tech.root: ifsk
ms.assetid: 83e8389f-1960-4fe0-9a33-526311ecba82
ms.date: 05/13/2019
keywords: ["FltSendMessage function"]
ms.keywords: FltApiRef_p_to_z_17d1087d-2a25-4c72-aed4-9246b4610b8b.xml, FltSendMessage, FltSendMessage function [Installable File System Drivers], fltkernel/FltSendMessage, ifsk.fltsendmessage
f1_keywords:
 - "fltkernel/FltSendMessage"
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Windows Server 2003 SP1, and later operating systems. Not available in Windows 2000 SP4 and earlier operating systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltSendMessage
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltSendMessage function

## -description

**FltSendMessage** sends a message to a waiting user-mode application on behalf of a minifilter driver or a minifilter driver instance.

## -parameters

### -param Filter [in]

Opaque filter pointer for the caller. This parameter is required and cannot be **NULL**.

### -param ClientPort [in]

Pointer to a variable that contains the opaque client port pointer for the connection port between the user-mode application and the kernel-mode minifilter driver. For more information about the client port pointer, see the description of the *ConnectNotifyCallback* parameter in the reference entry for [FltCreateCommunicationPort](nf-fltkernel-fltcreatecommunicationport.md).

### -param SenderBuffer [in]

Pointer to a caller-allocated buffer containing the message to be sent to the user-mode application. This parameter is required and cannot be **NULL**.

### -param SenderBufferLength [in]

Size, in bytes, of the buffer that *SenderBuffer* points to. See **Remarks** for more information.

### -param ReplyBuffer [out, optional]

Pointer to a caller-allocated buffer that receives the reply, if any, from the application. This parameter is optional and can be **NULL**.

### -param ReplyLength [in, out]

Size, in bytes, of the buffer that *ReplyBuffer* points to. This parameter is optional, but must be non-**NULL** when *ReplyBuffer* is not **NULL**.

### -param Timeout [in, optional]

A pointer to a timeout value that specifies the total absolute or relative length of time, in units of 100 nanoseconds, for which the caller can be put into a wait state until the message is received by the user-mode application and until it receives a reply (if one is expected). Set to **NULL** if the caller can be put into a wait state indefinitely.

## -returns

**FltSendMessage** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_INSUFFICIENT_RESOURCES | **FltSendMessage** encountered a pool allocation failure. This is an error code. |
| STATUS_PORT_DISCONNECTED | The communication port has been disconnected. This is an error code. |
| STATUS_THREAD_IS_TERMINATING | The wait was interrupted because the thread has been terminated by an application or user. |
| STATUS_TIMEOUT | The *Timeout* interval expired before the message could be delivered or before a reply was received. This is a success code. |

## -remarks

**FltSendMessage** sends a message to a user-mode application on behalf of a minifilter driver or a minifilter driver instance.

If the application calls [FilterGetMessage](https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filtergetmessage) to get the message before the minifilter driver calls **FltSendMessage** to send it, the message is delivered immediately. This is typically the case when the application calls **FilterGetMessage** from inside a message loop.

Otherwise, if an application has not called to get a message, the minifilter driver is put into a wait state as follows:

* If *Timeout* is nonzero and the application calls **FilterGetMessage** before the *Timeout* interval expires, the message is delivered.

* If *Timeout* is nonzero and the application doesn't call **FilterGetMessage** before the *Timeout* interval expires, the message is not delivered, and **FltSendMessage** returns STATUS_TIMEOUT. (Note: STATUS_TIMEOUT is a success code.)

* If *Timeout* is zero, the minifilter driver is put into a wait state indefinitely. When the application calls **FilterGetMessage**, the message is delivered.

After the message is delivered, if *ReplyBuffer* is **NULL**, **FltSendMessage** returns STATUS_SUCCESS.

Otherwise, if *ReplyBuffer* is not **NULL**, the minifilter driver is put into a wait state as follows:

* If *Timeout* is nonzero and the application calls [FilterReplyMessage](https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterreplymessage) before the *Timeout* interval expires, the minifilter driver receives the reply, and **FltSendMessage** returns STATUS_SUCCESS.

* If *Timeout* is nonzero and the minifilter driver does not receive a reply before the *Timeout* interval expires, **FltSendMessage** returns STATUS_TIMEOUT. (Note: STATUS_TIMEOUT is a success code.)

* If *Timeout* is zero when the minifilter driver is waiting for the reply, the minifilter driver is put into a wait state indefinitely. When the application calls **FilterReplyMessage**, the minifilter driver receives the reply, and **FltSendMessage** returns STATUS_SUCCESS.

<div class="alert"><b>Important</b>    Due to (system-specific) structure <a href="https://docs.microsoft.com/windows-hardware/drivers/">padding</a> requirements, accuracy is required when you set the size of buffers that are associated with <b>FltSendMessage</b> and <a href="https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterreplymessage">FilterReplyMessage</a>. As an example, assume data must be sent (via <b>FilterReplyMessage</b>) to a minifilter.  The user-mode component might declare the following structure to do so:<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _REPLY_STRUCT
{
     FILTER_REPLY_HEADER Header;
     MY_STRUCTURE Data;  // The structure to be sent to the minifilter.
} REPLY_STRUCT, *PREPLY_STRUCT;</pre>
</td>
</tr>
</table></span></div>
<p class="note">Given this structure, it might seem obvious that the caller of <a href="https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterreplymessage">FilterReplyMessage</a> would set the <i>dwReplyBufferSize</i> parameter to <b>sizeof(REPLY_STRUCT)</b> and the *ReplyLength</i> parameter of <b>FltSendMessage</b> to the same value. However, because of structure padding idiosyncrasies, <b>sizeof(REPLY_STRUCT)</b> might be larger than <b>sizeof(FILTER_REPLY_HEADER) + sizeof(MY_STRUCT)</b>.  If this is the case, <b>FltSendMessage</b> returns STATUS_BUFFER_OVERFLOW.

<p class="note">Therefore, we recommend that you call <a href="https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterreplymessage">FilterReplyMessage</a> and <b>FltSendMessage</b> (leveraging the above example) by setting <i>dwReplyBufferSize</i> and <i>ReplyLength</i> both to s<b>izeof(FILTER_REPLY_HEADER) + sizeof(MY_STRUCT)</b> instead of <b>sizeof(REPLY_STRUCT)</b>. This ensures that any extra padding at the end of the REPLY_STRUCT structure is ignored.

</div>

## -see-also

[FilterGetMessage](https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filtergetmessage)

[FilterReplyMessage](https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterreplymessage)

[FilterSendMessage](https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filtersendmessage)

[FltCreateCommunicationPort](nf-fltkernel-fltcreatecommunicationport.md)
