---
UID: NF:hbaapi.HBA_RegisterForAdapterPortEvents
title: HBA_RegisterForAdapterPortEvents function
author: windows-driver-content
description: The HBA_RegisterForAdapterPortEvents routine registers the indicated user callback routine to call when a port event occurs.
old-location: storage\hba_registerforadapterportevents.htm
old-project: storage
ms.assetid: 596bfba5-7025-4cdc-b1f9-c8df546f6dac
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HBA_RegisterForAdapterPortEvents, HBA_RegisterForAdapterPortEvents routine [Storage Devices], fibreHBA_rtns_147e7408-58e4-47bc-8d3f-185c8ee68b83.xml, hbaapi/HBA_RegisterForAdapterPortEvents, storage.hba_registerforadapterportevents
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
-	HBA_RegisterForAdapterPortEvents
product: Windows
targetos: Windows
req.typenames: 
---

# HBA_RegisterForAdapterPortEvents function


## -description


The <b>HBA_RegisterForAdapterPortEvents</b> routine registers the indicated user callback routine to call when a port event occurs. 


## -parameters




### -param callback

Pointer to a callback routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557123">HBA_PORT_CALLBACK</a> that is called when an adapter is added to the system.


### -param UserData

TBD


### -param Handle

TBD


### -param PortWWN

Contains a 64-bit worldwide name (WWN) that uniquely identifies the HBA port from which port events are reported. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


### -param pCallbackHandle

TBD




#### - callbackHandle

Contains an opaque identifier that the user must pass to <a href="https://msdn.microsoft.com/library/windows/hardware/ff557175">HBA_RemoveCallback</a> to de-register the callback routine.


#### - handle

Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a> that identifies the HBA for which the adapter events are generated. 


#### - userData

Pointer to a buffer that is passed to the callback routine with each event. This data correlates the event with the source of the event registration. 


## -returns



The <b>HBA_RegisterForAdapterPortEvents</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, this member should have one of the following values.

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
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>
</td>
<td width="60%">
Returned if the HBA referenced by <i>handle</i> does not have a port with a name that matches the value in <i>PortWWN</i>.

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



For a list of port events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557123">HBA_PORT_CALLBACK</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557123">HBA_PORT_CALLBACK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557175">HBA_RemoveCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
 

 

