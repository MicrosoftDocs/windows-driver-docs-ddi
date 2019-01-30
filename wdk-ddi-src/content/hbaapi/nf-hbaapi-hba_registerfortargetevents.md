---
UID: NF:hbaapi.HBA_RegisterForTargetEvents
title: HBA_RegisterForTargetEvents function (hbaapi.h)
description: The HBA_RegisterForTargetEvents routine registers for target events with a specified target or with all targets associated with an adapter.
old-location: storage\hba_registerfortargetevents.htm
tech.root: storage
ms.assetid: a06f6757-e125-4f80-9594-a60fa1fef6e4
ms.date: 03/29/2018
ms.keywords: HBA_RegisterForTargetEvents, HBA_RegisterForTargetEvents routine [Storage Devices], fibreHBA_rtns_511fff45-f98b-4dbe-a74c-d577497f4e8c.xml, hbaapi/HBA_RegisterForTargetEvents, storage.hba_registerfortargetevents
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
-	HBA_RegisterForTargetEvents
product:
- Windows
targetos: Windows
req.typenames: 
---

# HBA_RegisterForTargetEvents function


## -description


The <b>HBA_RegisterForTargetEvents</b> routine registers for target events with a specified target or with all targets associated with an adapter. 


## -parameters




### -param callback

Pointer to a callback routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557123">HBA_PORT_CALLBACK</a> that is called when an adapter is added to the system.


### -param pUserData

<p>Pointer to a buffer that is passed to the callback routine with each event. This data correlates the event with the source of the event registration. </p>


### -param Handle

<p>Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/Ff557097(v=VS.85).aspx"><b>HBA_OpenAdapter</b></a> that identifies the HBA for which the adapter events are generated. </p>


### -param HbaPortWWN

<p>Contains a 64-bit worldwide name (WWN) that uniquely identifies the local HBA port from which the target was discovered. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification. </p>


### -param DiscoveredPortWWN

<p>Contains a 64-bit WWN that uniquely identifies the remote HBA port from which target events are reported. </p>


### -param pCallbackHandle

<p>Contains an opaque identifier that the user must pass to <a href="https://msdn.microsoft.com/library/Ff557175(v=VS.85).aspx"><b>HBA_RemoveCallback</b></a> to de-register the callback routine.</p>


### -param AllTargets

<p>Indicates, when nonzero, that the value in <i>discoveredPortWWN</i> will be ignored, and the callback will be called for events associated with all current and future discovered targets. If this member is 0, only events associated with the target specified by <i>discoveredPortWWN</i> will be reported. </p>




## -returns



The <b>HBA_RegisterForTargetEvents</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_RegisterForTargetEvents</b> returns one of the following values.

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
Returned if the callback registration was successful. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>
</td>
<td width="60%">
Returned if the HBA referenced by <i>handle</i> does not contain a port with a name that matches <i>discoveredPortWWN</i>. 

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



To stop event delivery, call <b>HBA_RemoveCallback</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557123">HBA_PORT_CALLBACK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557175">HBA_RemoveCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
 

 

