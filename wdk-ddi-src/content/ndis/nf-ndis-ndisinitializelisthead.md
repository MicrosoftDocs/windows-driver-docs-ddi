---
UID: NF:ndis.NdisInitializeListHead
title: NdisInitializeListHead macro (ndis.h)
description: The NdisInitializeListHead function initializes a doubly linked, driver-maintained queue.
old-location: netvista\ndisinitializelisthead.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisInitializeListHead macro"]
ms.keywords: NdisInitializeListHead, NdisInitializeListHead macro [Network Drivers Starting with Windows Vista], ndis/NdisInitializeListHead, ndis_interlocked_ref_35d40751-6f2b-43db-801d-40479f3e0b6b.xml, netvista.ndisinitializelisthead
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisInitializeListHead (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisInitializeListHead (NDIS   5.1)) in Windows XP.
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
req.lib: 
req.dll: 
req.irql: Any level (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisInitializeListHead
 - ndis/NdisInitializeListHead
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisInitializeListHead
---

# NdisInitializeListHead macro


## -description

The 
  <b>NdisInitializeListHead</b> function initializes a doubly linked, driver-maintained queue.

## -parameters

### -param _ListHead 

[in]
A pointer to driver-allocated nonpaged storage for the head of the interlocked queue or
     list.

## -remarks

<b>NdisInitializeListHead</b> can be called from a 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function or
    from a protocol driver's 
    <a href="/previous-versions/windows/embedded/gg156036(v=winembedded.80)">DriverEntry</a> routine
    if the driver queues requests internally. However, miniport drivers seldom set up internal queues because
    the NDIS library serializes requests and packets sent to miniport drivers.

Any NDIS driver that maintains an internal queue is responsible for synchronizing driver functions'
    accesses to queued entries. The 
    <b>NdisInterlocked<i>Xxx</i>List</b> functions ensure that only one driver function can access queued entries at any given moment,
    even if the driver is running on a multiprocessor computer, because the queue is protected by a
    caller-supplied spin lock.

For an interlocked queue, the driver also must provide nonpaged storage for a spin lock. It must
    initialize the spin lock with the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a> function before
    passing a pointer to that spin lock to any of the 
    <b>NdisInterlocked<i>Xxx</i>List</b> functions.

Callers of <b>NdisInitializeListHead</b> can be running at any IRQL. If <b>NdisInitializeListHead</b> is called at IRQL >= DISPATCH_LEVEL the storage for <i>ListHead</i> must be resident.

## -see-also

<a href="/previous-versions/windows/embedded/gg156036(v=winembedded.80)">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinterlockedinsertheadlist">
   NdisInterlockedInsertHeadList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinterlockedinserttaillist">
   NdisInterlockedInsertTailList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinterlockedremoveheadlist">
   NdisInterlockedRemoveHeadList</a>
