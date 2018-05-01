---
UID: NF:hbaapi.HBA_RegisterForAdapterEvents
title: HBA_RegisterForAdapterEvents function
author: windows-driver-content
description: The HBA_RegisterForAdapterEvents routine registers the indicated user callback routine to call when an adapter event occurs.
old-location: storage\hba_registerforadapterevents.htm
old-project: storage
ms.assetid: b5e671dc-0583-4e5f-b537-3257b3f25479
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HBA_RegisterForAdapterEvents, HBA_RegisterForAdapterEvents routine [Storage Devices], fibreHBA_rtns_8ab64c5b-ffac-4e2a-90db-5f3cbc640f14.xml, hbaapi/HBA_RegisterForAdapterEvents, storage.hba_registerforadapterevents
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	HBA_RegisterForAdapterEvents
product: Windows
targetos: Windows
req.typenames: 
---

# HBA_RegisterForAdapterEvents function


## -description


The <b>HBA_RegisterForAdapterEvents</b> routine registers the indicated user callback routine to call when an adapter event occurs. 


## -parameters




### -param callback

Pointer to a callback routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556045">HBA_ADAPTER_CALLBACK</a> that is called when an adapter is added to the system.


### -param pUserData

TBD


### -param Handle

TBD


### -param pCallbackHandle

TBD




#### - callbackHandle

Contains an opaque identifier that the user must pass to <a href="https://msdn.microsoft.com/library/windows/hardware/ff557175">HBA_RemoveCallback</a> to de-register the callback routine.


#### - handle

Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a> that identifies the HBA for which the adapter events are generated. 


#### - userData

Pointer to a buffer that is passed to the callback routine with each event. This data correlates the event with the source of the event registration. 


## -returns



The <b>HBA_RegisterForAdapterEvents</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, this member should have one of the following values.

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



If the HBA referenced by <i>handle </i>is removed from the system, the callback function is called with event type of HBA_EVENT_ADAPTER_REMOVE.

If the configuration of the HBA referenced by <i>handle </i>is changed, the callback function is called with event type of HBA_EVENT_ADAPTER_CHANGE.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556045">HBA_ADAPTER_CALLBACK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557175">HBA_RemoveCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
 

 

