---
UID: NF:fltkernel.FltPropagateActivityIdToThread
title: FltPropagateActivityIdToThread function
author: windows-driver-content
description: The FltPropagateActivityIdToThread routine associates the activity ID from the IRP in the minifilter's callback data with the current thread.
old-location: ifsk\fltpropagateactivityidtothread.htm
old-project: ifsk
ms.assetid: 7453EEB1-F974-4AEB-93C4-A75A79E1FE19
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltPropagateActivityIdToThread, FltPropagateActivityIdToThread routine [Installable File System Drivers], fltkernel/FltPropagateActivityIdToThread, ifsk.fltpropagateactivityidtothread
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
-	FltPropagateActivityIdToThread
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltPropagateActivityIdToThread function


## -description


The <b>FltPropagateActivityIdToThread</b> routine associates the activity ID from the  IRP in the minifilter's callback data with the current thread.


## -parameters




### -param CallbackData [in]

A pointer to the callback data containing the request with an associated activity ID.


### -param PropagateId

TBD


### -param OriginalId [out]

On return, the <b>GUID</b> pointer referenced by <i>OriginalId</i> points to the activity ID that was previously set for the thread.


#### - PropagatedId [in, out]

A pointer to a caller allocated <b>GUID</b> which stores the activity ID for the current thread.


## -returns



<b>FltPropagateActivityIdToThread</b> returns one of the following <b>NTSTATUS</b> values.

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
 




## -remarks



The <b>FltPropagateActivityIdToThread</b> routine is  used by trace aware minifilters. A minifilter will use this routine to attach the activity ID from an IRP   to a worker thread processing I/O for the request.

    A minifilter must call <b>IoClearActivityIdThread</b> with the pointer in <i>OriginalId</i> before
    returning control from the worker thread if the call to <b>FltPropagateActivityIdToThread</b> was successful.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh967698">FltGetActivityIdCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh967702">FltSetActivityIdCallbackData</a>
 

 

