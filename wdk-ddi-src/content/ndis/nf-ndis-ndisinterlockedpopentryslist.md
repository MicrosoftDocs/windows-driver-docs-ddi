---
UID: NF:ndis.NdisInterlockedPopEntrySList
title: NdisInterlockedPopEntrySList macro (ndis.h)
description: The NdisInterlockedPopEntrySList function removes the first entry from a sequenced, singly linked list.
old-location: netvista\ndisinterlockedpopentryslist.htm
tech.root: netvista
ms.assetid: 22f79bc7-49e1-43ba-8dff-8847b9a9bcca
ms.date: 05/02/2018
keywords: ["NdisInterlockedPopEntrySList macro"]
ms.keywords: NdisInterlockedPopEntrySList, NdisInterlockedPopEntrySList macro [Network Drivers Starting with Windows Vista], ndis/NdisInterlockedPopEntrySList, ndis_interlocked_ref_5e66ef00-4498-4599-be50-f21ef676d032.xml, netvista.ndisinterlockedpopentryslist
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisInterlockedPopEntrySList   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisInterlockedPopEntrySList   (NDIS 5.1)) in Windows XP.
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisInterlockedPopEntrySList
 - ndis/NdisInterlockedPopEntrySList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisInterlockedPopEntrySList
---

# NdisInterlockedPopEntrySList macro


## -description

The
  <b>NdisInterlockedPopEntrySList</b> function removes the first entry from a sequenced, singly linked
  list.

## -parameters

### -param SListHead

A pointer to the head of the already initialized sequenced, singly linked list from which the
     entry is to be returned.

### -param Lock 

[in]
A pointer to a caller-supplied spin lock, not currently held by the caller.

## -remarks

A driver 
    <u>must not</u> be holding the given 
    <i>Lock</i> when it calls 
    <b>NdisInterlockedPopEntrySList</b>. If necessary, the driver should call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreleasespinlock">NdisReleaseSpinLock</a> function before
    making this call. 
    <b>NdisInterlockedPopEntrySList</b> itself must acquire this spin lock to remove the first entry in the
    S-List, if any, in a multiprocessor-safe way.

The caller must provide resident storage for the 
    <i>Lock</i>, which must be initialized with the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a> function before
    the initial call to any 
    <b>NdisInterlocked..SList</b> function.

If 
    <b>NdisInterlockedPopEntrySList</b> is called at IRQL >= DISPATCH_LEVEL, the storage for the 
    <i>ListHead</i> parameter must be resident.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreespinlock">NdisFreeSpinLock</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinitializeslisthead">NdisInitializeSListHead</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinterlockedpushentryslist">
   NdisInterlockedPushEntrySList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisquerydepthslist">NdisQueryDepthSList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreleasespinlock">NdisReleaseSpinLock</a>