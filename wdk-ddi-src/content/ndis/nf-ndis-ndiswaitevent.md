---
UID: NF:ndis.NdisWaitEvent
title: NdisWaitEvent function (ndis.h)
description: The NdisWaitEvent function puts the caller into a wait state until the given event is set to the Signaled state or the wait times out.
old-location: netvista\ndiswaitevent.htm
tech.root: netvista
ms.assetid: fefdb56f-6689-4a4f-a198-6108190624f0
ms.date: 05/02/2018
keywords: ["NdisWaitEvent function"]
ms.keywords: NdisWaitEvent, NdisWaitEvent function [Network Drivers Starting with Windows Vista], ndis/NdisWaitEvent, ndis_event_ref_d607d02a-0509-4399-90e8-bbfb43d613b3.xml, netvista.ndiswaitevent
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisWaitEvent (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisWaitEvent (NDIS 5.1)) in Windows   XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisWaitEvent
 - ndis/NdisWaitEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisWaitEvent
---

# NdisWaitEvent function


## -description

The
  <b>NdisWaitEvent</b> function puts the caller into a wait state until the given event is set to the Signaled
  state or the wait times out.

## -parameters

### -param Event 

[in]
A pointer to an initialized event object for which the caller provides the storage.

### -param MsToWait 

[in]
The number of milliseconds the caller will wait if the event is not set to the 
     <i>signaled</i> state within that interval. A value of zero specifies that the caller will wait for the
     event indefinitely.

## -returns

<b>NdisWaitEvent</b> returns <b>TRUE</b> if the event is in the 
     <i>signaled</i> state when the wait is satisfied.

## -remarks

<b>NdisWaitEvent</b> returns control to its caller when the given event is signaled or the specified 
    <i>MsToWait</i> interval expires, whichever is sooner. If the event is currently in the 
    <i>signaled</i> state when this call occurs, 
    <b>NdisWaitEvent</b> returns control immediately.

A miniport driver typically calls 
    <b>NdisWaitEvent</b> from its 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> and 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> functions. A protocol
    driver typically calls 
    <b>NdisWaitEvent</b> from its 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a> and 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_unbind_adapter_ex">
    ProtocolUnbindAdapterEx</a> functions.

## -see-also

<a href="/previous-versions/windows/embedded/gg156036(v=winembedded.80)">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinitializeevent">NdisInitializeEvent</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisresetevent">NdisResetEvent</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetevent">NdisSetEvent</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_unbind_adapter_ex">ProtocolUnbindAdapterEx</a>