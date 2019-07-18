---
UID: NF:ndis.NdisInterlockedPushEntrySList
title: NdisInterlockedPushEntrySList macro (ndis.h)
description: The NdisInterlockedPushEntrySList function inserts an entry at the head of a sequenced, singly linked list.
old-location: netvista\ndisinterlockedpushentryslist.htm
tech.root: netvista
ms.assetid: 155604e9-45f6-4dd2-9373-90f689713c1a
ms.date: 05/02/2018
ms.keywords: NdisInterlockedPushEntrySList, NdisInterlockedPushEntrySList macro [Network Drivers Starting with Windows Vista], ndis/NdisInterlockedPushEntrySList, ndis_interlocked_ref_ee1513c8-bb1a-4f3e-981b-7c448b3d1e41.xml, netvista.ndisinterlockedpushentryslist
ms.topic: macro
f1_keywords:
 - "ndis/NdisInterlockedPushEntrySList"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisInterlockedPushEntrySList (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisInterlockedPushEntrySList (NDIS 5.1)) in Windows XP.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NdisInterlockedPushEntrySList
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisInterlockedPushEntrySList macro


## -description


The 
  <b>NdisInterlockedPushEntrySList</b> function inserts an entry at the head of a sequenced, singly linked
  list.


## -parameters




### -param SListHead

A pointer to the head of the already initialized sequenced, singly linked list into which the
     specified entry is to be inserted.

### -param SListEntry

A pointer to the entry to be inserted.


### -param Lock [in]

A pointer to a caller-supplied spin lock, not currently held by the caller.

## -remarks



Before the driver's initial call the 
    <b>NdisInterlockedPushEntrySList</b> function, it must initialize the list head with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisinitializeslisthead">
    NdisInitializeSListHead</a> function.

A driver 
    <u>must not</u> be holding the given 
    <i>Lock</i> when it calls 
    <b>NdisInterlockedPushEntrySList</b>. If necessary, a driver must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisreleasespinlock">NdisReleaseSpinLock</a> function before
    calling 
    <b>NdisInterlockedPushEntrySList</b>. 
    <b>NdisInterlockedPushEntrySList</b> must acquire this lock itself before it inserts 
    <i>ListEntry</i> at the head of the list to ensure that this operation is handled in a multiprocessor-safe
    way.

The caller must provide resident storage for the 
    <i>Lock</i>, which must be initialized with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a> function before
    the initial call to any 
    <b>NdisInterlocked..SList</b> routine.

Drivers that retry I/O operations should use a doubly linked interlocked queue and the 
    <b>NdisInterlockedInsert/Remove..List</b> functions, instead of an S-List.

If 
    <b>NdisInterlockedPushEntrySList</b> is called at IRQL >= DISPATCH_LEVEL, the storage for the 
    <i>ListHead</i> parameter and the list entries must be resident




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisfreespinlock">NdisFreeSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisinitializeslisthead">NdisInitializeSListHead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisinterlockedpopentryslist">NdisInterlockedPopEntrySList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisquerydepthslist">NdisQueryDepthSList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisreleasespinlock">NdisReleaseSpinLock</a>
 

 

