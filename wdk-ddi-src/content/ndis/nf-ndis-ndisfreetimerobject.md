---
UID: NF:ndis.NdisFreeTimerObject
title: NdisFreeTimerObject function (ndis.h)
description: The NdisFreeTimerObject function frees a timer object that was allocated with the NdisAllocateTimerObject function.
old-location: netvista\ndisfreetimerobject.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisFreeTimerObject function"]
ms.keywords: NdisFreeTimerObject, NdisFreeTimerObject function [Network Drivers Starting with Windows Vista], ndis/NdisFreeTimerObject, ndis_timer_ref_0f4b2edb-47fb-481c-a1e9-6940d15cb354.xml, netvista.ndisfreetimerobject
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Timer_Function
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
 - NdisFreeTimerObject
 - ndis/NdisFreeTimerObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisFreeTimerObject
---

# NdisFreeTimerObject function


## -description

The 
  <b>NdisFreeTimerObject</b> function frees a timer object that was allocated with the 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatetimerobject">
  NdisAllocateTimerObject</a> function.

## -parameters

### -param TimerObject [in]


A handle to a timer object that NDIS provides when a driver calls the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatetimerobject">
     NdisAllocateTimerObject</a> function.

## -remarks

To use timer services, an NDIS driver first calls the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatetimerobject">NdisAllocateTimerObject</a> function
    to initialize a timer object. Typically, 
    <b>NdisAllocateTimerObject</b> is called when a driver initializes. The driver must call 
    <b>NdisFreeTimerObject</b> to free the timer object when the timer is no longer required.

To cancel a timer, call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscanceltimerobject">NdisCancelTimerObject</a> function. 
    <b>NdisCancelTimerObject</b> dequeues the timer object if it is currently queued.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_timer_characteristics">NDIS_TIMER_CHARACTERISTICS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatetimerobject">NdisAllocateTimerObject</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscanceltimerobject">NdisCancelTimerObject</a>
