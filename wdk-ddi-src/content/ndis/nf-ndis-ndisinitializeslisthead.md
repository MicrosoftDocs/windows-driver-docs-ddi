---
UID: NF:ndis.NdisInitializeSListHead
title: NdisInitializeSListHead macro
description: The NdisInitializeSListHead function initializes the head of a sequenced, interlocked, singly linked list.
old-location: netvista\ndisinitializeslisthead.htm
tech.root: netvista
ms.assetid: 4f9a5f8c-5c7f-4ac5-a6ce-118de2b4a304
ms.date: 05/02/2018
ms.keywords: NdisInitializeSListHead, NdisInitializeSListHead macro [Network Drivers Starting with Windows Vista], ndis/NdisInitializeSListHead, ndis_interlocked_ref_f27e10a0-22f5-48b2-a7d9-c5b4ffc85617.xml, netvista.ndisinitializeslisthead
ms.topic: macro
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisInitializeSListHead
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisInitializeSListHead macro


## -description


The 
  <b>NdisInitializeSListHead</b> function initializes the head of a sequenced, interlocked, singly linked
  list.


## -parameters




### -param SListHead [in]

A pointer to the caller-supplied list head to be initialized, which must be in resident
     memory. The structure must be 16-byte aligned on 64-bit platforms.


## -remarks



<b>NdisInitializeSListHead</b> zero-initializes the opaque list head at 
    <i>SListHead</i> and sets the first-entry pointer to <b>NULL</b>.

The sequence number in an S-List is incremented each time an entry is inserted to, or removed from,
    the list.

All entries in an S-List must be nonpaged.

Any driver that uses an S-List must provide a spin lock to the 
    <a href="https://msdn.microsoft.com/155604e9-45f6-4dd2-9373-90f689713c1a">
    NdisInterlockedPushEntrySList</a> and 
    <a href="https://msdn.microsoft.com/22f79bc7-49e1-43ba-8dff-8847b9a9bcca">
    NdisInterlockedPopEntrySList</a> functions. Before its initial call to either of these functions, the
    driver must initialize the spin lock with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561617">NdisAllocateSpinLock</a> function. To
    prevent deadlocks, the driver 
    <u>must not be holding this spin lock</u> when it makes subsequent calls to 
    <b>NdisInterlockedPushEntrySList</b> and 
    <b>NdisInterlockedPopEntrySList</b>.

To manage a pool of fixed-size entries from nonpaged memory, consider using a lookaside list instead
    of an S-List.

Drivers that retry I/O operations should use a doubly linked interlocked queue and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562754">NdisInterlockedInsertHeadList</a>,  <a href="https://msdn.microsoft.com/library/windows/hardware/ff562755">NdisInterlockedInsertTailList</a>, and   <a href="https://msdn.microsoft.com/library/windows/hardware/ff562771">NdisInterlockedRemoveHeadList</a> functions, rather than an S-List.

If 
    <b>NdisInitializeSListHead</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for the 
    <i>SListHead</i> parameter must be resident.




## -see-also




<a href="https://msdn.microsoft.com/d240f2cc-18a6-4c2d-889f-e25a9486d5fe">
   NdisInitializeNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562760">NdisInterlockedPopEntrySList</a>



<a href="https://msdn.microsoft.com/155604e9-45f6-4dd2-9373-90f689713c1a">
   NdisInterlockedPushEntrySList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563753">NdisQueryDepthSList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563775">NdisQueueIoWorkItem</a>
 

 

