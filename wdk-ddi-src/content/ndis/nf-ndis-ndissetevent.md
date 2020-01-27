---
UID: NF:ndis.NdisSetEvent
title: NdisSetEvent function (ndis.h)
description: The NdisSetEvent function sets a given event to the signaled state if it was not already Signaled.
old-location: netvista\ndissetevent.htm
tech.root: netvista
ms.assetid: 3f45b8d0-2d5b-4601-a307-48257cdcb4ba
ms.date: 05/02/2018
ms.keywords: NdisSetEvent, NdisSetEvent function [Network Drivers Starting with Windows Vista], ndis/NdisSetEvent, ndis_event_ref_3abf6ebc-6dcf-4b3e-8e39-2902b9b00adf.xml, netvista.ndissetevent
f1_keywords:
 - "ndis/NdisSetEvent"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisSetEvent (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisSetEvent (NDIS 5.1)) in Windows   XP.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisSetEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisSetEvent function


## -description


The 
  <b>NdisSetEvent</b> function sets a given event to the signaled state if it was not already Signaled.


## -parameters




### -param Event [in]

A pointer to an initialized event object for which the caller provides the storage.


## -remarks



When an event attains the 
    <i>signaled</i> state, it causes waits on the event to be satisfied and any waiters to be dispatched for
    execution.

After a call to 
    <b>NdisSetEvent</b>, the event remains in the 
    <i>signaled</i> state until the driver calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisresetevent">NdisResetEvent</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinitializeevent">NdisInitializeEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisresetevent">NdisResetEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswaitevent">NdisWaitEvent</a>
 

 

