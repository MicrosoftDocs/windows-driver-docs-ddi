---
UID: NF:wdm.SeEtwWriteKMCveEvent
title: SeEtwWriteKMCveEvent function
author: windows-driver-content
description: The SeEtwWriteKMCveEvent function is a tracing function for publishing events when an attempted security vulnerability exploit is detected in your kernel-mode drivers.
old-location: devtest\seetwwritekmcveevent.htm
old-project: devtest
ms.assetid: 9CF6C8FC-869A-4667-9859-845BFF093549
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: SeEtwWriteKMCveEvent, SeEtwWriteKMCveEvent function [Display Devices], devtest.seetwwritekmcveevent, wdm/SeEtwWriteKMCveEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10 and later versions of Windows
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
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Ntoskrnl.exe
api_name:
-	SeEtwWriteKMCveEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# SeEtwWriteKMCveEvent function


## -description


The <b> 	SeEtwWriteKMCveEvent</b> function is a tracing function for publishing events when an attempted security vulnerability exploit is detected in your kernel-mode drivers.   


## -parameters




### -param CveId [in]

A pointer to a string mentioning the CVE-ID associated with the vulnerability for which this event is being raised. Technical guidance for handling the CVE-ID is shared <a href="ttp://go.microsoft.com/fwlink/?LinkId=798519">here</a>


### -param AdditionalDetails [in, optional]

A pointer to a string giving additional details that the event producer may want to provide to the consumer of this event.


## -returns



<b>SeEtwWriteKMCveEvent</b> returns one of the following values:

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
The driver was successfully published

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ERROR_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Invalid pointer to CVE-ID passed

<div class="alert"><b>Note</b>  Events can be lost for several reasons; for example, if the event rate is too high or if the event size is greater than the buffer size. In these cases, the <b>EventsLost</b> counter, a member of the <a href="https://msdn.microsoft.com/0c967971-8df1-4679-a8a9-a783f5b35860">EVENT_TRACE_PROPERTIES</a> structure for the corresponding logger, is updated with the number of events that were not recorded.</div>
<div> </div>
</td>
</tr>
</table>
 




## -remarks



The <b> 	SeEtwWriteKMCveEvent</b> function publishes a CVE-based event. This function should be called only in scenarios where an attempt to exploit a known, patched vulnerability is detected by the application. Ideally, this function call should be added as part of the fix (update) itself. 
 The default consumer for this event is EventLog-System. To enable another consumer, the provider can be added to the consumer session.


Provider GUID: 85a62a0d-7e17-485f-9d4f-749a287193a6

Source Name: Microsoft-Windows-Audit-CVE or CVE-Audit


#### Examples

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>//

NTStatus status;
UNICODE_STRING CVEID;
UNICODE_STRING EventDetails;

…

RtlInitUnicodeString(&amp;CVEID, L“CVE-2015-0000”);
RtlInitUnicodeString(&amp;EventDetails, L”Vulnerable request with data is logged in %temp%\abc.log”);

status = SeEtwWriteKMCveEvent( &amp;CVEID, &amp;EventDetails);

//
</pre>
</td>
</tr>
</table></span></div>


