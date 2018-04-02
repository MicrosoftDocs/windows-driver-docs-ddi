---
UID: NF:ndis.NdisInterlockedRemoveHeadList
title: NdisInterlockedRemoveHeadList macro
author: windows-driver-content
description: The NdisInterlockedRemoveHeadList function removes an entry, usually a packet, from the head of a doubly linked list so that access to the list is synchronized in a multiprocessor-safe way.
old-location: netvista\ndisinterlockedremoveheadlist.htm
old-project: netvista
ms.assetid: 85cbc158-7132-4666-8161-a78251a62e4d
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisInterlockedRemoveHeadList, NdisInterlockedRemoveHeadList macro [Network Drivers Starting with Windows Vista], ndis/NdisInterlockedRemoveHeadList, ndis_interlocked_ref_5aacd492-068c-4cfe-afa6-4e0e63cf66e9.xml, netvista.ndisinterlockedremoveheadlist
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisInterlockedRemoveHeadList
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisInterlockedRemoveHeadList macro


## -description


The 
  <b>NdisInterlockedRemoveHeadList</b> function removes an entry, usually a packet, from the head of a doubly
  linked list so that access to the list is synchronized in a multiprocessor-safe way.


## -parameters




### -param _ListHead [in]

A pointer to the head of the doubly linked list from which an entry is to be removed.


### -param _SpinLock [in]

A pointer to a caller-supplied spin lock, used to synchronize access to the list.


## -remarks



Before calling any 
    <b>NdisInterlocked..List</b> function, a driver must initialize the variable at 
    <i>ListHead</i> with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562734">NdisInitializeListHead</a> function and
    the variable at 
    <i>SpinLock</i> with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561617">NdisAllocateSpinLock</a> function. The
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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542043">CONTAINING_RECORD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561617">NdisAllocateSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562734">NdisInitializeListHead</a>



<a href="https://msdn.microsoft.com/c6221ce9-682c-453b-b036-f4219c9540da">
   NdisInterlockedInsertHeadList</a>



<a href="https://msdn.microsoft.com/cc455bb1-3574-4dfb-9462-f2c67632132b">
   NdisInterlockedInsertTailList</a>
 

 

