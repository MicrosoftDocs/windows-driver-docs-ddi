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
ms.keywords: FltSendMessage function [Installable File System Drivers], FltSendMessage, ifsk.fltsendmessage, FltApiRef_p_to_z_17d1087d-2a25-4c72-aed4-9246b4610b8b.xml, fltkernel/FltSendMessage
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltSendMessage
product: Windows
targetos: Windows
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




#### - Filter [in]

Opaque filter pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


#### - ClientPort [in]

A pointer to a variable that contains the opaque client port pointer for the connection port between the user-mode application and the kernel-mode minifilter driver. For more information about the client port pointer, see the description of the <i>ConnectNotifyCallback</i> parameter in the reference entry for <a href="..\fltkernel\nf-fltkernel-fltcreatecommunicationport.md">FltCreateCommunicationPort</a>. 


#### - SenderBuffer [in]

A pointer to a caller-allocated buffer containing the message to be sent to the user-mode application. This parameter is required and cannot be <b>NULL</b>. 


#### - SenderBufferLength [in]

Size, in bytes, of the buffer that <i>SenderBuffer </i>points to. See Remarks.


#### - ReplyBuffer [out, optional]

A pointer to a caller-allocated buffer that receives the reply (if any) from the application. This parameter is optional and can be <b>NULL</b>. 


#### - ReplyLength [in, out]

Size, in bytes, of the buffer that <i>ReplyBuffer </i>points to. 


#### - Timeout [in, optional]

A pointer to a timeout value that specifies the total absolute or relative length of time, in units of 100 nanoseconds, for which the caller can be put into a wait state until the message is received by the user-mode application and until it receives a reply (if one is expected). Set to <b>NULL</b> if the caller can be put into a wait state indefinitely. 


## -returns


<b>FltSendMessage</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltSendMessage</b> encountered a pool allocation failure. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PORT_DISCONNECTED</b></dt>
</dl>
</td>
<td width="60%">
The communication port has been disconnected. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
The <i>Timeout</i> interval expired before the message could be delivered or before a reply was received. This is a success code. 

</td>
</tr>
</table> 



## -remarks


<b>FltSendMessage</b> sends a message to a user-mode application on behalf of a minifilter driver or a minifilter driver instance. 

If the application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff540506">FilterGetMessage</a> to get the message before the minifilter driver calls <b>FltSendMessage</b> to send it, the message is delivered immediately. (This is typically the case when the application calls <b>FilterGetMessage</b> from inside a message loop.) 

Otherwise, if <i>Timeout</i> is nonzero, the minifilter driver is put into a wait state as follows: 
<ul>
<li>
If the application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff540506">FilterGetMessage</a> before the <i>Timeout</i> interval expires, the message is delivered. 

</li>
<li>
Otherwise, the message is not delivered, and <b>FltSendMessage</b> returns STATUS_TIMEOUT. (Note: STATUS_TIMEOUT is a success code.) 

</li>
</ul>If <i>Timeout</i> is zero when the message is being sent, the minifilter driver is put into a wait state indefinitely. When the application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff540506">FilterGetMessage</a>, the message is delivered. 

After the message is delivered, if <i>ReplyBuffer</i> is <b>NULL</b>, <b>FltSendMessage</b> returns STATUS_SUCCESS. 

Otherwise, if <i>Timeout</i> is nonzero, the minifilter driver is put into a wait state as follows: 
<ul>
<li>
If the application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff541508">FilterReplyMessage</a> before the <i>Timeout</i> interval expires, the minifilter driver receives the reply, and <b>FltSendMessage</b> returns STATUS_SUCCESS. 

</li>
<li>
Otherwise, the minifilter driver does not receive a reply, and <b>FltSendMessage</b> returns STATUS_TIMEOUT. (Note: STATUS_TIMEOUT is a success code.) 

</li>
</ul>If <i>Timeout</i> is zero when the minifilter driver is waiting for the reply, the minifilter driver is put into a wait state indefinitely. When the application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff541508">FilterReplyMessage</a>, the minifilter driver receives the reply, and <b>FltSendMessage</b> returns STATUS_SUCCESS.
<div class="alert"><b>Important</b>    Due to (system-specific) structure <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">padding</a> requirements, accuracy is required when you set the size of buffers that are associated with <b>FltSendMessage</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff541508">FilterReplyMessage</a>. As an example, assume data must be sent (via <b>FilterReplyMessage</b>) to a minifilter.  The user-mode component might declare the following structure to do so:<div class="code"><span codelanguage=""><table>
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
<p class="note">Given this structure, it might seem obvious that the caller of <a href="https://msdn.microsoft.com/library/windows/hardware/ff541508">FilterReplyMessage</a> would set the <i>dwReplyBufferSize</i> parameter to <b>sizeof(REPLY_STRUCT)</b> and the <i>ReplyLength</i> parameter of <b>FltSendMessage</b> to the same value.  However, because of structure padding idiosyncrasies, <b>sizeof(REPLY_STRUCT)</b> might be larger than <b>sizeof(FILTER_REPLY_HEADER) + sizeof(MY_STRUCT)</b>.  If this is the case, <b>FltSendMessage</b> returns STATUS_BUFFER_OVERFLOW.

<p class="note">Therefore, we recommend that you call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541508">FilterReplyMessage</a> and <b>FltSendMessage</b> (leveraging the above example) by setting <i>dwReplyBufferSize</i> and <i>ReplyLength</i> both to s<b>izeof(FILTER_REPLY_HEADER) + sizeof(MY_STRUCT)</b> instead of <b>sizeof(REPLY_STRUCT)</b>. This ensures that any extra padding at the end of the REPLY_STRUCT structure is ignored.

</div><div> </div>


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540506">FilterGetMessage</a>

<a href="..\fltkernel\nf-fltkernel-fltcreatecommunicationport.md">FltCreateCommunicationPort</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541508">FilterReplyMessage</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541513">FilterSendMessage</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltSendMessage function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

