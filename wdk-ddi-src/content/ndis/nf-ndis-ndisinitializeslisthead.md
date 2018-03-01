---
UID: NF:ndis.NdisInitializeSListHead
title: NdisInitializeSListHead macro
author: windows-driver-content
description: The NdisInitializeSListHead function initializes the head of a sequenced, interlocked, singly linked list.
old-location: netvista\ndisinitializeslisthead.htm
old-project: netvista
ms.assetid: 4f9a5f8c-5c7f-4ac5-a6ce-118de2b4a304
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisInitializeSListHead, NdisInitializeSListHead macro [Network Drivers Starting with Windows Vista], ndis/NdisInitializeSListHead, ndis_interlocked_ref_f27e10a0-22f5-48b2-a7d9-c5b4ffc85617.xml, netvista.ndisinitializeslisthead
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: ndis.h
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
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisInitializeSListHead macro


## -description


The 
  <b>NdisInitializeSListHead</b> function initializes the head of a sequenced, interlocked, singly linked
  list.


## -syntax


````
VOID NdisInitializeSListHead(
  [in] PSLIST_HEADER SListHead
);
````


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
    <a href="..\ndis\nf-ndis-ndisinterlockedpushentryslist.md">
    NdisInterlockedPushEntrySList</a> and 
    <a href="..\ndis\nf-ndis-ndisinterlockedpopentryslist.md">
    NdisInterlockedPopEntrySList</a> functions. Before its initial call to either of these functions, the
    driver must initialize the spin lock with the 
    <a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a> function. To
    prevent deadlocks, the driver 
    <u>must not be holding this spin lock</u> when it makes subsequent calls to 
    <b>NdisInterlockedPushEntrySList</b> and 
    <b>NdisInterlockedPopEntrySList</b>.

To manage a pool of fixed-size entries from nonpaged memory, consider using a lookaside list instead
    of an S-List.

Drivers that retry I/O operations should use a doubly linked interlocked queue and the <a href="..\ndis\nf-ndis-ndisinterlockedinsertheadlist.md">NdisInterlockedInsertHeadList</a>,  <a href="..\ndis\nf-ndis-ndisinterlockedinserttaillist.md">NdisInterlockedInsertTailList</a>, and   <a href="..\ndis\nf-ndis-ndisinterlockedremoveheadlist.md">NdisInterlockedRemoveHeadList</a> functions, rather than an S-List.

If 
    <b>NdisInitializeSListHead</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for the 
    <i>SListHead</i> parameter must be resident.




## -see-also

<a href="..\ndis\nf-ndis-ndisqueueioworkitem.md">NdisQueueIoWorkItem</a>



<a href="..\ndis\nf-ndis-ndisinterlockedpopentryslist.md">NdisInterlockedPopEntrySList</a>



<a href="..\ndis\nf-ndis-ndisinitializenpagedlookasidelist.md">
   NdisInitializeNPagedLookasideList</a>



<a href="..\ndis\nf-ndis-ndisinterlockedpushentryslist.md">
   NdisInterlockedPushEntrySList</a>



<a href="..\ndis\nf-ndis-ndisquerydepthslist.md">NdisQueryDepthSList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisInitializeSListHead macro%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

