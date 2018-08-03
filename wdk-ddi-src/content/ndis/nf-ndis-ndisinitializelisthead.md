---
UID: NF:ndis.NdisInitializeListHead
title: NdisInitializeListHead macro
author: windows-driver-content
description: The NdisInitializeListHead function initializes a doubly linked, driver-maintained queue.
old-location: netvista\ndisinitializelisthead.htm
tech.root: netvista
ms.assetid: da3f5f28-2794-491b-a359-be8508b050bf
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NdisInitializeListHead, NdisInitializeListHead macro [Network Drivers Starting with Windows Vista], ndis/NdisInitializeListHead, ndis_interlocked_ref_35d40751-6f2b-43db-801d-40479f3e0b6b.xml, netvista.ndisinitializelisthead
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisInitializeListHead
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisInitializeListHead macro


## -description


The 
  <b>NdisInitializeListHead</b> function initializes a doubly linked, driver-maintained queue.


## -parameters




### -param _ListHead [in]

A pointer to driver-allocated nonpaged storage for the head of the interlocked queue or
     list.


## -remarks



<b>NdisInitializeListHead</b> can be called from a 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function or
    from a protocol driver's 
    <a href="https://msdn.microsoft.com/en-us/library/gg156036.aspx">DriverEntry</a> routine
    if the driver queues requests internally. However, miniport drivers seldom set up internal queues because
    the NDIS library serializes requests and packets sent to miniport drivers.

Any NDIS driver that maintains an internal queue is responsible for synchronizing driver functions'
    accesses to queued entries. The 
    <b>NdisInterlocked<i>Xxx</i>List</b> functions ensure that only one driver function can access queued entries at any given moment,
    even if the driver is running on a multiprocessor computer, because the queue is protected by a
    caller-supplied spin lock.

For an interlocked queue, the driver also must provide nonpaged storage for a spin lock. It must
    initialize the spin lock with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561617">NdisAllocateSpinLock</a> function before
    passing a pointer to that spin lock to any of the 
    <b>NdisInterlocked<i>Xxx</i>List</b> functions.

Callers of <b>NdisInitializeListHead</b> can be running at any IRQL. If <b>NdisInitializeListHead</b> is called at IRQL &gt;= DISPATCH_LEVEL the storage for <i>ListHead</i> must be resident.




## -see-also




<a href="https://msdn.microsoft.com/en-us/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561617">NdisAllocateSpinLock</a>



<a href="https://msdn.microsoft.com/c6221ce9-682c-453b-b036-f4219c9540da">
   NdisInterlockedInsertHeadList</a>



<a href="https://msdn.microsoft.com/cc455bb1-3574-4dfb-9462-f2c67632132b">
   NdisInterlockedInsertTailList</a>



<a href="https://msdn.microsoft.com/85cbc158-7132-4666-8161-a78251a62e4d">
   NdisInterlockedRemoveHeadList</a>
 

 

