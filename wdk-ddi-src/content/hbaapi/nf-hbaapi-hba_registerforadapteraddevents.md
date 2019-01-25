---
UID: NF:hbaapi.HBA_RegisterForAdapterAddEvents
title: HBA_RegisterForAdapterAddEvents function (hbaapi.h)
description: The HBA_RegisterForAdapterAddEvents routine registers the indicated user callback routine to call when a new adapter is added to the system.
old-location: storage\hba_registerforadapteraddevents.htm
tech.root: storage
ms.assetid: 7395ccb8-2608-46ae-a378-987bd757761b
ms.date: 03/29/2018
ms.keywords: HBA_RegisterForAdapterAddEvents, HBA_RegisterForAdapterAddEvents routine [Storage Devices], fibreHBA_rtns_d44e8303-9d14-4f36-830e-bca76a494dfd.xml, hbaapi/HBA_RegisterForAdapterAddEvents, storage.hba_registerforadapteraddevents
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_RegisterForAdapterAddEvents
product:
- Windows
targetos: Windows
req.typenames: 
---

# HBA_RegisterForAdapterAddEvents function


## -description


The <b>HBA_RegisterForAdapterAddEvents</b> routine registers the indicated user callback routine to call when a new adapter is added to the system. 


## -parameters




### -param callback [in]

Pointer to a callback routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556045">HBA_ADAPTER_CALLBACK</a> that is called when an adapter is added to the system.


### -param pUserData

<p>Pointer to a buffer that will be passed to the callback routine with each event. This data correlates the event with the source of the event registration. </p>


### -param pCallbackHandle

<p>Contains an opaque identifier that the user must pass to <a href="https://msdn.microsoft.com/library/Ff557175(v=VS.85).aspx"><b>HBA_RemoveCallback</b></a> to de-register the callback routine.</p>




## -returns



The <b>HBA_RegisterForAdapterAddEvents</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, this member should have one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>
</td>
<td width="60%">
Returned if the callback routine was successfully registered. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the registration of the callback routine. 

</td>
</tr>
</table>
 




## -remarks



When a new adapter is added to the system, an event of type HBA_EVENT_ADAPTER_ADD is generated.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556045">HBA_ADAPTER_CALLBACK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557175">HBA_RemoveCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
 

 

