---
UID: NF:wdm.SeEtwWriteKMCveEvent
title: SeEtwWriteKMCveEvent function
author: windows-driver-content
description: The SeEtwWriteKMCveEvent function is a tracing function for publishing events when an attempted security vulnerability exploit is detected in your kernel-mode drivers.
old-location: devtest\seetwwritekmcveevent.htm
old-project: devtest
ms.assetid: 9CF6C8FC-869A-4667-9859-845BFF093549
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: SeEtwWriteKMCveEvent
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
req.alt-api: SeEtwWriteKMCveEvent
req.alt-loc: Ntoskrnl.exe
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# SeEtwWriteKMCveEvent function



## -description
The <b> 	SeEtwWriteKMCveEvent</b> function is a tracing function for publishing events when an attempted security vulnerability exploit is detected in your kernel-mode drivers.   



## -syntax

````
__checkReturn HRESULT NTStatus SeEtwWriteKMCveEvent(
  _In_     PCUNICODE_STRING CveId,
  _In_opt_ PCUNICODE_STRING AdditionalDetails
);
````


## -parameters

### -param CveId [in]

A pointer to a string mentioning the CVE-ID associated with the vulnerability for which this event is being raised. Technical guidance for handling the CVE-ID is shared <a href="ttp://go.microsoft.com/fwlink/?LinkId=798519">here</a>


### -param AdditionalDetails [in, optional]

A pointer to a string giving additional details that the event producer may want to provide to the consumer of this event.


## -returns
<b>SeEtwWriteKMCveEvent</b> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The driver was successfully published
<dl>
<dt><b>ERROR_INVALID_PARAMETER</b></dt>
</dl>Invalid pointer to CVE-ID passed

 


## -remarks
The <b> 	SeEtwWriteKMCveEvent</b> function publishes a CVE-based event. This function should be called only in scenarios where an attempt to exploit a known, patched vulnerability is detected by the application. Ideally, this function call should be added as part of the fix (update) itself. 
 The default consumer for this event is EventLog-System. To enable another consumer, the provider can be added to the consumer session.


Provider GUID: 85a62a0d-7e17-485f-9d4f-749a287193a6

Source Name: Microsoft-Windows-Audit-CVE or CVE-Audit</p>