---
UID: NF:fltkernel.FltSetActivityIdCallbackData
title: FltSetActivityIdCallbackData function
author: windows-driver-content
description: The FltSetActivityIdCallbackData routine sets the a activity ID for an IRP in a minifilter's callback data.
old-location: ifsk\fltsetactivityidcallbackdata.htm
old-project: ifsk
ms.assetid: D7CA9DAB-E350-42D5-A008-5CC12D5313D3
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltSetActivityIdCallbackData, FltSetActivityIdCallbackData routine [Installable File System Drivers], fltkernel/FltSetActivityIdCallbackData, ifsk.fltsetactivityidcallbackdata
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 8.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltSetActivityIdCallbackData
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltSetActivityIdCallbackData function


## -description


The <b>FltSetActivityIdCallbackData</b> routine sets the a activity ID for an IRP in a minifilter's callback data.


## -parameters




### -param CallbackData [in, out]

A pointer to the callback data containing the request with an associated activity ID.


### -param Guid [in, optional]

A optional pointer to the <b>GUID</b> structure receiving the activity ID. if <i>Guid</i> is <b>NULL</b>, the system will attempt to assign an ETW activity ID for the request.


## -returns



<b>FltSetActivityIdCallbackData</b> returns one of the following <b>NTSTATUS</b> values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The callback data does not contain a request for an IRP operation.

-or-

The <b>GUID</b> pointed to by <i>Guid</i> is was not provided and no ETW activity ID is available or the operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No activity ID is associated with the request in <i>CallbackData</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
An activity ID pointed to by <i>Guid</i> was set for the IRP in <i>CallbackData</i>.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh967698">FltGetActivityIdCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh967700">FltPropagateActivityIdToThread</a>
 

 

