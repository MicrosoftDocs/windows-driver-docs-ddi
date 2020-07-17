---
UID: NF:fltkernel.FltGetActivityIdCallbackData
title: FltGetActivityIdCallbackData function (fltkernel.h)
description: The FltGetActivityIdCallbackData routine retrieves the current activity ID associated with a request in a minifilter's callback data.
old-location: ifsk\fltgetactivityidcallbackdata.htm
tech.root: ifsk
ms.assetid: 3DAA2135-768E-4A37-B2FD-9915F16D8A66
ms.date: 04/16/2018
keywords: ["FltGetActivityIdCallbackData function"]
ms.keywords: FltGetActivityIdCallbackData, FltGetActivityIdCallbackData routine [Installable File System Drivers], fltkernel/FltGetActivityIdCallbackData, ifsk.fltgetactivityidcallbackdata
f1_keywords:
 - "fltkernel/FltGetActivityIdCallbackData"
 - "FltGetActivityIdCallbackData"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltGetActivityIdCallbackData
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetActivityIdCallbackData function


## -description


The <b>FltGetActivityIdCallbackData</b> routine retrieves the current activity ID associated with a request in a minifilter's callback data.


## -parameters




### -param CallbackData [in]

A pointer to the callback data containing the request with an associated activity ID.


### -param Guid [out]

A pointer to the GUID structure receiving the activity ID.


## -returns



<b>FltGetActivityIdCallbackData</b> returns one of the following <b>NTSTATUS</b> values.

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
An activity ID was returned in the <b>GUID</b> value pointed to by <i>Guid</i>.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltpropagateactivityidtothread">FltPropagateActivityIdToThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetactivityidcallbackdata">FltSetActivityIdCallbackData</a>
 

 

