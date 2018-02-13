---
UID: NF:wdm.WmiTraceMessage
title: WmiTraceMessage function
author: windows-driver-content
description: The WmiTraceMessage routine adds a message to the output log of a WPP software tracing session.
old-location: kernel\wmitracemessage.htm
old-project: kernel
ms.assetid: 045c45fe-c971-4d41-a43d-415c2a4d464b
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.wmitracemessage, WmiTraceMessage routine [Kernel-Mode Driver Architecture], WmiTraceMessage, wdm/WmiTraceMessage, k902_114717ae-d439-4ddd-b939-913795610dee.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	WmiTraceMessage
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# WmiTraceMessage function


## -description


The <b>WmiTraceMessage</b> routine adds a message to the output log of a <a href="https://msdn.microsoft.com/dab776b3-bac9-4157-a530-6e48868ba900">WPP software tracing</a> session.


## -syntax


````
NTSTATUS WmiTraceMessage(
  _In_ TRACEHANDLE LoggerHandle,
  _In_ ULONG       MessageFlags,
  _In_ LPCGUID     MessageGuid,
  _In_ USHORT      MessageNumber,
  _In_             ...
);
````


## -parameters




### -param LoggerHandle [in]

Specifies a trace handle for a software tracing session.


### -param MessageFlags [in]

Specifies a bitwise OR of one or more message flags. See the Remarks section for details.


### -param MessageGuid [in]

Specifies a GUID that identifies the class of software trace messages.


### -param MessageNumber [in]

Identifies the message subtype. The meaning of subtypes is specific to the software trace class and the provider.


### -param param

TBD




####### - ... [in]

Provides a required list of message parameters that specify a set of message parts. The parameters are organized as a sequence of parameter pairs, where each pair specifies one part of the complete message. Each parameter pair consists of a PVOID pointer to data, followed immediately by a ULONG value that specifies the length of the data. The parameter list must be terminated by a <b>NULL</b> PVOID pointer followed by a ULONG(0).


## -returns



<b>WmiTraceMessage</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
<i>LoggerHandle</i> is not a valid software trace handle.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
There is insufficient buffer memory to log the message. See the Remarks section.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other NTSTATUS value</b></dt>
</dl>
</td>
<td width="60%">
An internal error occurred.

</td>
</tr>
</table>
 




## -remarks



A caller can use <b>WmiTraceMessage</b> or <a href="..\wdm\nf-wdm-wmitracemessageva.md">WmiTraceMessageVa</a> to add a message to the output log of a WPP software tracing session. <b>WmiTraceMessage</b> simplifies a caller's code by handling the variable list mechanism before calling <b>WmiTraceMessageVa</b>.

A caller can set the following message flags:

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
TRACE_MESSAGE_SEQUENCE

</td>
<td>
Include a sequence number in the message. Message sequencing can only be used if it is set for the software tracing session specified by <i>LoggerHandle</i>.

</td>
</tr>
<tr>
<td>
TRACE_MESSAGE_GUID

</td>
<td>
<i>MessageGuid</i> specifies a GUID that identifies a software trace class. This flag must be set.

</td>
</tr>
<tr>
<td>
TRACE_MESSAGE_TIMESTAMP

</td>
<td>
Include a time stamp in the message.

</td>
</tr>
<tr>
<td>
TRACE_MESSAGE_PERFORMANCE_TIMESTAMP

</td>
<td>
This flag is not implemented and is <u>obsolete</u>. It must not be used. 

</td>
</tr>
<tr>
<td>
TRACE_MESSAGE_SYSTEMINFO

</td>
<td>
Include the thread identifier (TID) and process identifier (PID) in the message.

</td>
</tr>
</table>
 

A message will not be logged if one of the following is true:

<ul>
<li>
The total size, in bytes, of the message data and the message header is greater than the size of individual message buffers allocated for a software tracing session. (The maximum message header size is 48 bytes.)

</li>
<li>
All message buffers allocated to software tracing session are full. 

</li>
</ul>
<b>WmiTraceMessage</b> runs at the IRQL of the caller.




## -see-also

<a href="..\wdm\ne-wdm-_trace_information_class.md">TRACE_INFORMATION_CLASS</a>



<a href="..\wdm\nf-wdm-iowmiwriteevent.md">IoWmiWriteEvent</a>



<a href="..\wdm\nf-wdm-wmiquerytraceinformation.md">WmiQueryTraceInformation</a>



<a href="..\wdm\nf-wdm-wmitracemessageva.md">WmiTraceMessageVa</a>



<a href="..\wmilib\nf-wmilib-wmifireevent.md">WmiFireEvent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WmiTraceMessage routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

