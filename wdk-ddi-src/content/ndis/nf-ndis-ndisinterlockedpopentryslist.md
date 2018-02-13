---
UID: NF:ndis.NdisInterlockedPopEntrySList
title: NdisInterlockedPopEntrySList macro
author: windows-driver-content
description: The NdisInterlockedPopEntrySList function removes the first entry from a sequenced, singly linked list.
old-location: netvista\ndisinterlockedpopentryslist.htm
old-project: netvista
ms.assetid: 22f79bc7-49e1-43ba-8dff-8847b9a9bcca
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/NdisInterlockedPopEntrySList, ndis_interlocked_ref_5e66ef00-4498-4599-be50-f21ef676d032.xml, NdisInterlockedPopEntrySList, netvista.ndisinterlockedpopentryslist, NdisInterlockedPopEntrySList macro [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
-	NdisInterlockedPopEntrySList
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisInterlockedPopEntrySList macro


## -description


The
  <b>NdisInterlockedPopEntrySList</b> function removes the first entry from a sequenced, singly linked
  list.


## -syntax


````
PSINGLE_LIST_ENTRY NdisInterlockedPopEntrySList(
  [in] PSLIST_HEADER   ListHead,
  [in] PNDIS_SPIN_LOCK Lock
);
````


## -parameters




### -param SListHead

TBD


### -param Lock [in]

A pointer to a caller-supplied spin lock, not currently held by the caller.


#### - ListHead [in]

A pointer to the head of the already initialized sequenced, singly linked list from which the
     entry is to be returned.


## -remarks



A driver 
    <u>must not</u> be holding the given 
    <i>Lock</i> when it calls 
    <b>NdisInterlockedPopEntrySList</b>. If necessary, the driver should call the 
    <a href="..\ndis\nf-ndis-ndisreleasespinlock.md">NdisReleaseSpinLock</a> function before
    making this call. 
    <b>NdisInterlockedPopEntrySList</b> itself must acquire this spin lock to remove the first entry in the
    S-List, if any, in a multiprocessor-safe way.

The caller must provide resident storage for the 
    <i>Lock</i>, which must be initialized with the 
    <a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a> function before
    the initial call to any 
    <b>NdisInterlocked..SList</b> function.

If 
    <b>NdisInterlockedPopEntrySList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for the 
    <i>ListHead</i> parameter must be resident.




## -see-also

<a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a>



<a href="..\ndis\nf-ndis-ndisquerydepthslist.md">NdisQueryDepthSList</a>



<a href="..\ndis\nf-ndis-ndisinterlockedpushentryslist.md">
   NdisInterlockedPushEntrySList</a>



<a href="..\ndis\nf-ndis-ndisreleasespinlock.md">NdisReleaseSpinLock</a>



<a href="..\ndis\nf-ndis-ndisfreespinlock.md">NdisFreeSpinLock</a>



<a href="..\ndis\nf-ndis-ndisinitializeslisthead.md">NdisInitializeSListHead</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisInterlockedPopEntrySList macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

