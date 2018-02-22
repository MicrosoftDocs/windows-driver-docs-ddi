---
UID: NF:ndis.NdisInterlockedRemoveHeadList
title: NdisInterlockedRemoveHeadList macro
author: windows-driver-content
description: The NdisInterlockedRemoveHeadList function removes an entry, usually a packet, from the head of a doubly linked list so that access to the list is synchronized in a multiprocessor-safe way.
old-location: netvista\ndisinterlockedremoveheadlist.htm
old-project: netvista
ms.assetid: 85cbc158-7132-4666-8161-a78251a62e4d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisInterlockedRemoveHeadList macro [Network Drivers Starting with Windows Vista], NdisInterlockedRemoveHeadList, ndis/NdisInterlockedRemoveHeadList, netvista.ndisinterlockedremoveheadlist, ndis_interlocked_ref_5aacd492-068c-4cfe-afa6-4e0e63cf66e9.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisInterlockedRemoveHeadList (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisInterlockedRemoveHeadList (NDIS 5.1)) in Windows XP.
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
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisInterlockedRemoveHeadList
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisInterlockedRemoveHeadList macro


## -description


The 
  <b>NdisInterlockedRemoveHeadList</b> function removes an entry, usually a packet, from the head of a doubly
  linked list so that access to the list is synchronized in a multiprocessor-safe way.


## -syntax


````
PLIST_ENTRY NdisInterlockedRemoveHeadList(
  [in] PLIST_ENTRY     ListHead,
  [in] PNDIS_SPIN_LOCK SpinLock
);
````


## -parameters




### -param _ListHead [in]

A pointer to the head of the doubly linked list from which an entry is to be removed.


### -param _SpinLock [in]

A pointer to a caller-supplied spin lock, used to synchronize access to the list.


## -remarks



Before calling any 
    <b>NdisInterlocked..List</b> function, a driver must initialize the variable at 
    <i>ListHead</i> with the 
    <a href="..\ndis\nf-ndis-ndisinitializelisthead.md">NdisInitializeListHead</a> function and
    the variable at 
    <i>SpinLock</i> with the 
    <a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a> function. The
    driver also must provide resident storage for these variables and for its internal queue.

Before calling 
    <b>NdisInterlockedRemoveHeadList</b>, entries are queued with one or more calls to the 
    <b>NdisInterlockedInsert..List</b> functions.

The caller-supplied spin lock prevents any other function from accessing the driver's internal queue
    while 
    <b>NdisInterlockedRemoveHeadList</b> is removing an entry, even when the driver is running on a
    multiprocessor computer.

<b>NdisInterlockedRemoveHeadList</b> raises the IRQL to DISPATCH_LEVEL when it acquires the given spin
    lock and restores the original IRQL before it returns control. Consequently, any driver function that
    calls 
    <b>NdisInterlockedRemoveHeadList</b> cannot be pageable code.

To convert a returned value back to the address of the inserted entry, a driver can use the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff542043">CONTAINING_RECORD</a> macro.

If 
    <b>NdisInterlockedRemoveHeadList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for the 
    <i>ListHead</i> parameter must be resident.




## -see-also

<a href="..\ndis\nf-ndis-ndisinterlockedinserttaillist.md">
   NdisInterlockedInsertTailList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542043">CONTAINING_RECORD</a>



<a href="..\ndis\nf-ndis-ndisinitializelisthead.md">NdisInitializeListHead</a>



<a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a>



<a href="..\ndis\nf-ndis-ndisinterlockedinsertheadlist.md">
   NdisInterlockedInsertHeadList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisInterlockedRemoveHeadList macro%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

