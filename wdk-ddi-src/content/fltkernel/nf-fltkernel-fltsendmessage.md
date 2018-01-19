---
UID: NF:fltkernel.FltSendMessage
title: FltSendMessage function
author: windows-driver-content
description: FltSendMessage sends a message to a waiting user-mode application on behalf of a minifilter driver or a minifilter driver instance.
old-location: ifsk\fltsendmessage.htm
old-project: ifsk
ms.assetid: 83e8389f-1960-4fe0-9a33-526311ecba82
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltSendMessage
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Windows Server 2003 SP1, and later operating systems. Not available in Windows 2000 SP4 and earlier operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltSendMessage
req.alt-loc: fltmgr.sys
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
req.typenames: EXpsFontRestriction
---

# FltSendMessage function



## -description
<b>FltSendMessage</b> sends a message to a waiting user-mode application on behalf of a minifilter driver or a minifilter driver instance. 



## -syntax

````
NTSTATUS FltSendMessage(
  _In_      PFLT_FILTER    Filter,
  _In_      PFLT_PORT      *ClientPort,
  _In_      PVOID          SenderBuffer,
  _In_      ULONG          SenderBufferLength,
  _Out_opt_ PVOID          ReplyBuffer,
  _Inout_   PULONG         ReplyLength,
  _In_opt_  PLARGE_INTEGER Timeout
);
````


## -parameters

### -param Filter [in]

Opaque filter pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param ClientPort [in]

A pointer to a variable that contains the opaque client port pointer for the connection port between the user-mode application and the kernel-mode minifilter driver. For more information about the client port pointer, see the description of the <i>ConnectNotifyCallback</i> parameter in the reference entry for <a href="..\fltkernel\nf-fltkernel-fltcreatecommunicationport.md">FltCreateCommunicationPort</a>. 


### -param SenderBuffer [in]

A pointer to a caller-allocated buffer containing the message to be sent to the user-mode application. This parameter is required and cannot be <b>NULL</b>. 


### -param SenderBufferLength [in]

Size, in bytes, of the buffer that <i>SenderBuffer </i>points to. See Remarks.


### -param ReplyBuffer [out, optional]

A pointer to a caller-allocated buffer that receives the reply (if any) from the application. This parameter is optional and can be <b>NULL</b>. 


### -param ReplyLength [in, out]

Size, in bytes, of the buffer that <i>ReplyBuffer </i>points to. 


### -param Timeout [in, optional]

A pointer to a timeout value that specifies the total absolute or relative length of time, in units of 100 nanoseconds, for which the caller can be put into a wait state until the message is received by the user-mode application and until it receives a reply (if one is expected). Set to <b>NULL</b> if the caller can be put into a wait state indefinitely. 


## -returns
<b>FltSendMessage</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><b>FltSendMessage</b> encountered a pool allocation failure. This is an error code. 
<dl>
<dt><b>STATUS_PORT_DISCONNECTED</b></dt>
</dl>The communication port has been disconnected. This is an error code. 
<dl>
<dt><b>STATUS_TIMEOUT</b></dt>
</dl>The <i>Timeout</i> interval expired before the message could be delivered or before a reply was received. This is a success code. 

 


## -remarks
<b>FltSendMessage</b> sends a message to a user-mode application on behalf of a minifilter driver or a minifilter driver instance. 

If the application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff540506">FilterGetMessage</a> to get the message before the minifilter driver calls <b>FltSendMessage</b> to send it, the message is delivered immediately. (This is typically the case when the application calls <b>FilterGetMessage</b> from inside a message loop.) 

Otherwise, if <i>Timeout</i> is nonzero, the minifilter driver is put into a wait state as follows: 

If the application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff540506">FilterGetMessage</a> before the <i>Timeout</i> interval expires, the message is delivered. 

Otherwise, the message is not delivered, and <b>FltSendMessage</b> returns STATUS_TIMEOUT. (Note: STATUS_TIMEOUT is a success code.) 

If <i>Timeout</i> is zero when the message is being sent, the minifilter driver is put into a wait state indefinitely. When the application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff540506">FilterGetMessage</a>, the message is delivered. 

After the message is delivered, if <i>ReplyBuffer</i> is <b>NULL</b>, <b>FltSendMessage</b> returns STATUS_SUCCESS. 

If the application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff541508">FilterReplyMessage</a> before the <i>Timeout</i> interval expires, the minifilter driver receives the reply, and <b>FltSendMessage</b> returns STATUS_SUCCESS. 

Otherwise, the minifilter driver does not receive a reply, and <b>FltSendMessage</b> returns STATUS_TIMEOUT. (Note: STATUS_TIMEOUT is a success code.) 

If <i>Timeout</i> is zero when the minifilter driver is waiting for the reply, the minifilter driver is put into a wait state indefinitely. When the application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff541508">FilterReplyMessage</a>, the minifilter driver receives the reply, and <b>FltSendMessage</b> returns STATUS_SUCCESS.
<p class="note">Given this structure, it might seem obvious that the caller of <a href="https://msdn.microsoft.com/library/windows/hardware/ff541508">FilterReplyMessage</a> would set the <i>dwReplyBufferSize</i> parameter to <b>sizeof(REPLY_STRUCT)</b> and the <i>ReplyLength</i> parameter of <b>FltSendMessage</b> to the same value.  However, because of structure padding idiosyncrasies, <b>sizeof(REPLY_STRUCT)</b> might be larger than <b>sizeof(FILTER_REPLY_HEADER) + sizeof(MY_STRUCT)</b>.  If this is the case, <b>FltSendMessage</b> returns STATUS_BUFFER_OVERFLOW.
<p class="note">Therefore, we recommend that you call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541508">FilterReplyMessage</a> and <b>FltSendMessage</b> (leveraging the above example) by setting <i>dwReplyBufferSize</i> and <i>ReplyLength</i> both to s<b>izeof(FILTER_REPLY_HEADER) + sizeof(MY_STRUCT)</b> instead of <b>sizeof(REPLY_STRUCT)</b>. This ensures that any extra padding at the end of the REPLY_STRUCT structure is ignored.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540506">FilterGetMessage</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541513">FilterSendMessage</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541508">FilterReplyMessage</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcreatecommunicationport.md">FltCreateCommunicationPort</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltSendMessage function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

