---
UID: NF:ndis.NdisInterlockedPopEntrySList
title: NdisInterlockedPopEntrySList macro
author: windows-driver-content
description: The NdisInterlockedPopEntrySList function removes the first entry from a sequenced, singly linked list.
old-location: netvista\ndisinterlockedpopentryslist.htm
old-project: netvista
ms.assetid: 22f79bc7-49e1-43ba-8dff-8847b9a9bcca
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisInterlockedPopEntrySList, NdisInterlockedPopEntrySList macro [Network Drivers Starting with Windows Vista], ndis/NdisInterlockedPopEntrySList, ndis_interlocked_ref_5e66ef00-4498-4599-be50-f21ef676d032.xml, netvista.ndisinterlockedpopentryslist
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
-	NdisInterlockedPopEntrySList
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisInterlockedPopEntrySList macro


## -description


The
  <b>NdisInterlockedPopEntrySList</b> function removes the first entry from a sequenced, singly linked
  list.


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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564524">NdisReleaseSpinLock</a> function before
    making this call. 
    <b>NdisInterlockedPopEntrySList</b> itself must acquire this spin lock to remove the first entry in the
    S-List, if any, in a multiprocessor-safe way.

The caller must provide resident storage for the 
    <i>Lock</i>, which must be initialized with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561617">NdisAllocateSpinLock</a> function before
    the initial call to any 
    <b>NdisInterlocked..SList</b> function.

If 
    <b>NdisInterlockedPopEntrySList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for the 
    <i>ListHead</i> parameter must be resident.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561617">NdisAllocateSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562602">NdisFreeSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562739">NdisInitializeSListHead</a>



<a href="https://msdn.microsoft.com/155604e9-45f6-4dd2-9373-90f689713c1a">
   NdisInterlockedPushEntrySList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563753">NdisQueryDepthSList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564524">NdisReleaseSpinLock</a>
 

 

