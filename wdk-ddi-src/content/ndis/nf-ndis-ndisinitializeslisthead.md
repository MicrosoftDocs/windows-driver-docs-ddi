---
UID: NF:ndis.NdisInitializeSListHead
title: NdisInitializeSListHead macro (ndis.h)
description: The NdisInitializeSListHead function initializes the head of a sequenced, interlocked, singly linked list.
old-location: netvista\ndisinitializeslisthead.htm
tech.root: netvista
ms.assetid: 4f9a5f8c-5c7f-4ac5-a6ce-118de2b4a304
ms.date: 05/02/2018
keywords: ["NdisInitializeSListHead macro"]
ms.keywords: NdisInitializeSListHead, NdisInitializeSListHead macro [Network Drivers Starting with Windows Vista], ndis/NdisInitializeSListHead, ndis_interlocked_ref_f27e10a0-22f5-48b2-a7d9-c5b4ffc85617.xml, netvista.ndisinitializeslisthead
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisInitializeSListHead (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisInitializeSListHead (NDIS   5.1)) in Windows XP.
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
 - NdisInitializeSListHead
 - ndis/NdisInitializeSListHead
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisInitializeSListHead
---

# NdisInitializeSListHead macro


## -description

The 
  <b>NdisInitializeSListHead</b> function initializes the head of a sequenced, interlocked, singly linked
  list.

## -parameters

### -param SListHead 

[in]
A pointer to the caller-supplied list head to be initialized, which must be in resident
     memory. The structure must be 16-byte aligned on 64-bit platforms.

## -remarks

<b>NdisInitializeSListHead</b> zero-initializes the opaque list head at 
    <i>SListHead</i> and sets the first-entry pointer to <b>NULL</b>.

The sequence number in an S-List is incremented each time an entry is inserted to, or removed from,
    the list.

All entries in an S-List must be nonpaged.

Any driver that uses an S-List must provide a spin lock to the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinterlockedpushentryslist">
    NdisInterlockedPushEntrySList</a> and 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinterlockedpopentryslist">
    NdisInterlockedPopEntrySList</a> functions. Before its initial call to either of these functions, the
    driver must initialize the spin lock with the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a> function. To
    prevent deadlocks, the driver 
    <u>must not be holding this spin lock</u> when it makes subsequent calls to 
    <b>NdisInterlockedPushEntrySList</b> and 
    <b>NdisInterlockedPopEntrySList</b>.

To manage a pool of fixed-size entries from nonpaged memory, consider using a lookaside list instead
    of an S-List.

Drivers that retry I/O operations should use a doubly linked interlocked queue and the <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinterlockedinsertheadlist">NdisInterlockedInsertHeadList</a>,  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinterlockedinserttaillist">NdisInterlockedInsertTailList</a>, and   <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinterlockedremoveheadlist">NdisInterlockedRemoveHeadList</a> functions, rather than an S-List.

If 
    <b>NdisInitializeSListHead</b> is called at IRQL >= DISPATCH_LEVEL, the storage for the 
    <i>SListHead</i> parameter must be resident.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinitializenpagedlookasidelist">
   NdisInitializeNPagedLookasideList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinterlockedpopentryslist">NdisInterlockedPopEntrySList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinterlockedpushentryslist">
   NdisInterlockedPushEntrySList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisquerydepthslist">NdisQueryDepthSList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisqueueioworkitem">NdisQueueIoWorkItem</a>