---
UID: NF:hbaapi.HBA_RegisterForAdapterPortStatEvents
title: HBA_RegisterForAdapterPortStatEvents function
author: windows-driver-content
description: The HBA_RegisterForAdapterPortStatEvents routine registers the indicated user callback routine to call when a port statistics event occurs.
old-location: storage\hba_registerforadapterportstatevents.htm
old-project: storage
ms.assetid: 82598ba4-6e01-44eb-9359-4b85e8f7980c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HBA_RegisterForAdapterPortStatEvents
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
req.alt-api: HBA_RegisterForAdapterPortStatEvents
req.alt-loc: Hbaapi.dll
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
req.typenames: HBA_WWNTYPE
---

# HBA_RegisterForAdapterPortStatEvents function



## -description
The <b>HBA_RegisterForAdapterPortStatEvents</b> routine registers the indicated user callback routine to call when a port statistics event occurs. 



## -syntax

````
HBA_STATUS HBA_API HBA_RegisterForAdapterPortStatEvents(
   HBA_PORTSTAT_CALLBACK callback,
   void                  *userData,
   HBA_HANDLE            handle,
   HBA_WWN               PortWWN,
   PHBA_PORTSTATISTICS   stats,
   HBA_UINT32            statType,
   HBA_CALLBACKHANDLE    *callbackHandle
);
````


## -parameters

### -param callback 

Pointer to a callback routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557117">HBA_PORTSTAT_CALLBACK</a> that is called when an adapter is added to the system.


### -param userData 

Pointer to a buffer that is passed to the callback routine with each event. This data correlates the event with the source of the event registration. 


### -param handle 

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA for which the adapter events are generated. 


### -param PortWWN 

Contains a 64-bit worldwide name (WWN) that uniquely identifies the HBA port from which port events are reported. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


### -param stats 

Pointer to a structure of type <a href="..\hbaapi\ns-hbaapi-hba_portstatistics.md">HBA_PortStatistics</a> that, on input, holds the statistical levels that determine when port statistics events are generated. On output, this member holds statistical data gathered for the port referenced by <i>PortWWN. </i>


### -param statType 

Holds a value that indicates the mechanism used to trigger port statistics events. If the value is HBA_EVENT_PORT_STAT_THRESHOLD, then each non-NULL member of the HBA_PortStatistics structure pointed to by <i>stats </i>will indicate the threshold at which an event is generated for that particular statistical parameter. For example, if the <b>TxWords</b> member of the HBA_PortStatistics structure holds a value of 1,000,000, then an event will be generated once 1,000,000 words have been transmitted.

If the value of <i>statType </i>is HBA_EVENT_PORT_STAT_GROWTH, then the values in the HBA_PortStatistics structure will be interpreted as growth-rate numbers. The T11 committee's <i>Fibre Channel HBA API</i> specification recommends that port statistics be checked once a minute, and if the value or a given statistics parameter has grown by more than the number indicated for that parameter in HBA_PortStatistics, an event is generated, but the actual frequency with which growth is monitored is hardware-specific.


### -param callbackHandle 

Pointer to an opaque identifier that the user must pass to <a href="..\hbaapi\nf-hbaapi-hba_removecallback.md">HBA_RemoveCallback</a> to de-register the callback routine.


## -returns
The <b>HBA_RegisterForAdapterPortStatEvents</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, this member should have one of the following values.
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>Returned if the callback routine was successfully registered. 
<dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>Returned if the HBA referenced by <i>handle</i> does not have a port with a name that matches the value in <i>PortWWN</i>.
<dl>
<dt><b>HBA_STATUS_ERROR_NOT_SUPPORTED</b></dt>
</dl>Returned if the hardware does not support statistic events. 
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>Returned if an unspecified error occurred that prevented the registration of the callback routine. 

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557117">HBA_PORTSTAT_CALLBACK</a>
</dt>
<dt>
<a href="..\hbaapi\ns-hbaapi-hba_portstatistics.md">HBA_PortStatistics</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_RegisterForAdapterPortStatEvents routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

