---
UID: NF:ndis.NdisInitializeListHead
title: NdisInitializeListHead macro
author: windows-driver-content
description: The NdisInitializeListHead function initializes a doubly linked, driver-maintained queue.
old-location: netvista\ndisinitializelisthead.htm
old-project: netvista
ms.assetid: da3f5f28-2794-491b-a359-be8508b050bf
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndisinitializelisthead, ndis/NdisInitializeListHead, NdisInitializeListHead, NdisInitializeListHead macro [Network Drivers Starting with Windows Vista], ndis_interlocked_ref_35d40751-6f2b-43db-801d-40479f3e0b6b.xml
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
req.lib: ndis.h
req.dll: 
req.irql: Any level (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NdisInitializeListHead
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisInitializeListHead macro


## -description


The 
  <b>NdisInitializeListHead</b> function initializes a doubly linked, driver-maintained queue.


## -syntax


````
VOID NdisInitializeListHead(
  [in] PLIST_ENTRY ListHead
);
````


## -parameters




### -param _ListHead [in]

A pointer to driver-allocated nonpaged storage for the head of the interlocked queue or
     list.


## -remarks



<b>NdisInitializeListHead</b> can be called from a 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function or
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
    <a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a> function before
    passing a pointer to that spin lock to any of the 
    <b>NdisInterlocked<i>Xxx</i>List</b> functions.

Callers of <b>NdisInitializeListHead</b> can be running at any IRQL. If <b>NdisInitializeListHead</b> is called at IRQL &gt;= DISPATCH_LEVEL the storage for <i>ListHead</i> must be resident.




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndisinterlockedinsertheadlist.md">
   NdisInterlockedInsertHeadList</a>



<a href="..\ndis\nf-ndis-ndisinterlockedremoveheadlist.md">
   NdisInterlockedRemoveHeadList</a>



<a href="..\ndis\nf-ndis-ndisinterlockedinserttaillist.md">
   NdisInterlockedInsertTailList</a>



<a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisInitializeListHead macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

