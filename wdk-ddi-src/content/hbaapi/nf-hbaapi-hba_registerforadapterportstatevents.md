---
UID: NF:hbaapi.HBA_RegisterForAdapterPortStatEvents
title: HBA_RegisterForAdapterPortStatEvents function
author: windows-driver-content
description: The HBA_RegisterForAdapterPortStatEvents routine registers the indicated user callback routine to call when a port statistics event occurs.
old-location: storage\hba_registerforadapterportstatevents.htm
old-project: storage
ms.assetid: 82598ba4-6e01-44eb-9359-4b85e8f7980c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HBA_RegisterForAdapterPortStatEvents, HBA_RegisterForAdapterPortStatEvents routine [Storage Devices], fibreHBA_rtns_38f8ecc4-4c08-4707-98f1-076602ecae27.xml, hbaapi/HBA_RegisterForAdapterPortStatEvents, storage.hba_registerforadapterportstatevents
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
-	HBA_RegisterForAdapterPortStatEvents
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_RegisterForAdapterPortStatEvents function


## -description


The <b>HBA_RegisterForAdapterPortStatEvents</b> routine registers the indicated user callback routine to call when a port statistics event occurs. 


## -parameters




### -param callback

Pointer to a callback routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557117">HBA_PORTSTAT_CALLBACK</a> that is called when an adapter is added to the system.


### -param pUserData

TBD


### -param Handle

TBD


### -param PortWWN

Contains a 64-bit worldwide name (WWN) that uniquely identifies the HBA port from which port events are reported. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


### -param stats

Pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557110">HBA_PortStatistics</a> that, on input, holds the statistical levels that determine when port statistics events are generated. On output, this member holds statistical data gathered for the port referenced by <i>PortWWN. </i>


### -param statType

Holds a value that indicates the mechanism used to trigger port statistics events. If the value is HBA_EVENT_PORT_STAT_THRESHOLD, then each non-NULL member of the HBA_PortStatistics structure pointed to by <i>stats </i>will indicate the threshold at which an event is generated for that particular statistical parameter. For example, if the <b>TxWords</b> member of the HBA_PortStatistics structure holds a value of 1,000,000, then an event will be generated once 1,000,000 words have been transmitted.

If the value of <i>statType </i>is HBA_EVENT_PORT_STAT_GROWTH, then the values in the HBA_PortStatistics structure will be interpreted as growth-rate numbers. The T11 committee's <i>Fibre Channel HBA API</i> specification recommends that port statistics be checked once a minute, and if the value or a given statistics parameter has grown by more than the number indicated for that parameter in HBA_PortStatistics, an event is generated, but the actual frequency with which growth is monitored is hardware-specific.


### -param pCallbackHandle

TBD




#### - callbackHandle

Pointer to an opaque identifier that the user must pass to <a href="https://msdn.microsoft.com/library/windows/hardware/ff557175">HBA_RemoveCallback</a> to de-register the callback routine.


#### - handle

Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a> that identifies the HBA for which the adapter events are generated. 


#### - userData

Pointer to a buffer that is passed to the callback routine with each event. This data correlates the event with the source of the event registration. 


## -returns



The <b>HBA_RegisterForAdapterPortStatEvents</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, this member should have one of the following values.

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
<dt><b>HBA_STATUS_ERROR_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
Returned if the hardware does not support statistic events. 

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
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557117">HBA_PORTSTAT_CALLBACK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557110">HBA_PortStatistics</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
 

 

