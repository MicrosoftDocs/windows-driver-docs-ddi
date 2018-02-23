---
UID: NF:ndis.NdisInterlockedPushEntrySList
title: NdisInterlockedPushEntrySList macro
author: windows-driver-content
description: The NdisInterlockedPushEntrySList function inserts an entry at the head of a sequenced, singly linked list.
old-location: netvista\ndisinterlockedpushentryslist.htm
old-project: netvista
ms.assetid: 155604e9-45f6-4dd2-9373-90f689713c1a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ndis/NdisInterlockedPushEntrySList, ndis_interlocked_ref_ee1513c8-bb1a-4f3e-981b-7c448b3d1e41.xml, NdisInterlockedPushEntrySList, netvista.ndisinterlockedpushentryslist, NdisInterlockedPushEntrySList macro [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
req.lib: ndis.h
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NdisInterlockedPushEntrySList
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisInterlockedPushEntrySList macro


## -description


The 
  <b>NdisInterlockedPushEntrySList</b> function inserts an entry at the head of a sequenced, singly linked
  list.


## -syntax


````
PSINGLE_LIST_ENTRY NdisInterlockedPushEntrySList(
  [in] PSLIST_HEADER      ListHead,
  [in] PSINGLE_LIST_ENTRY ListEntry,
  [in] PNDIS_SPIN_LOCK    Lock
);
````


## -parameters




### -param SListHead

TBD


### -param SListEntry

TBD


### -param Lock [in]

A pointer to a caller-supplied spin lock, not currently held by the caller.


#### - ListHead [in]

A pointer to the head of the already initialized sequenced, singly linked list into which the
     specified entry is to be inserted.


#### - ListEntry [in]

A pointer to the entry to be inserted.


## -remarks



Before the driver's initial call the 
    <b>NdisInterlockedPushEntrySList</b> function, it must initialize the list head with the 
    <a href="..\ndis\nf-ndis-ndisinitializeslisthead.md">
    NdisInitializeSListHead</a> function.

A driver 
    <u>must not</u> be holding the given 
    <i>Lock</i> when it calls 
    <b>NdisInterlockedPushEntrySList</b>. If necessary, a driver must call the 
    <a href="..\ndis\nf-ndis-ndisreleasespinlock.md">NdisReleaseSpinLock</a> function before
    calling 
    <b>NdisInterlockedPushEntrySList</b>. 
    <b>NdisInterlockedPushEntrySList</b> must acquire this lock itself before it inserts 
    <i>ListEntry</i> at the head of the list to ensure that this operation is handled in a multiprocessor-safe
    way.

The caller must provide resident storage for the 
    <i>Lock</i>, which must be initialized with the 
    <a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a> function before
    the initial call to any 
    <b>NdisInterlocked..SList</b> routine.

Drivers that retry I/O operations should use a doubly linked interlocked queue and the 
    <b>NdisInterlockedInsert/Remove..List</b> functions, instead of an S-List.

If 
    <b>NdisInterlockedPushEntrySList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for the 
    <i>ListHead</i> parameter and the list entries must be resident




## -see-also

<a href="..\ndis\nf-ndis-ndisinitializeslisthead.md">NdisInitializeSListHead</a>



<a href="..\ndis\nf-ndis-ndisfreespinlock.md">NdisFreeSpinLock</a>



<a href="..\ndis\nf-ndis-ndisinterlockedpopentryslist.md">NdisInterlockedPopEntrySList</a>



<a href="..\ndis\nf-ndis-ndisreleasespinlock.md">NdisReleaseSpinLock</a>



<a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a>



<a href="..\ndis\nf-ndis-ndisquerydepthslist.md">NdisQueryDepthSList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisInterlockedPushEntrySList macro%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

