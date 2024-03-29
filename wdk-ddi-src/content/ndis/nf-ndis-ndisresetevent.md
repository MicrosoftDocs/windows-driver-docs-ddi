---
UID: NF:ndis.NdisResetEvent
title: NdisResetEvent function (ndis.h)
description: The NdisResetEvent function clears the Signaled state of a given event.
old-location: netvista\ndisresetevent.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisResetEvent function"]
ms.keywords: NdisResetEvent, NdisResetEvent function [Network Drivers Starting with Windows Vista], ndis/NdisResetEvent, ndis_event_ref_2970c5ca-b236-41e4-b156-c283f4f637f9.xml, netvista.ndisresetevent
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisResetEvent (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisResetEvent (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Synch_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisResetEvent
 - ndis/NdisResetEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisResetEvent
---

# NdisResetEvent function


## -description

The
  <b>NdisResetEvent</b> function clears the Signaled state of a given event.

## -parameters

### -param Event [in]


A pointer to an initialized event object for which the caller provided the storage.

## -remarks

<b>NdisResetEvent</b> explicitly sets the state of the given event to 
    <i>not-signaled</i>.

When an event is set to the 
    <i>signaled</i> state with the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetevent">NdisSetEvent</a> function, it remains in that
    state until an explicit call to 
    <b>NdisResetEvent</b> occurs. While an event remains in the 
    <i>signaled</i> state, callers of the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswaitevent">NdisWaitEvent</a> function on that event are
    dispatched for execution without waiting.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinitializeevent">NdisInitializeEvent</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetevent">NdisSetEvent</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswaitevent">NdisWaitEvent</a>
