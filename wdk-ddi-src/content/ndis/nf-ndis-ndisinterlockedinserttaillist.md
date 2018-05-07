---
UID: NF:ndis.NdisInterlockedInsertTailList
title: NdisInterlockedInsertTailList macro
author: windows-driver-content
description: The NdisInterlockedInsertTailList function inserts an entry, usually a packet, at the tail of a doubly linked list so that access to the list is synchronized in a multiprocessor-safe way.
old-location: netvista\ndisinterlockedinserttaillist.htm
old-project: netvista
ms.assetid: cc455bb1-3574-4dfb-9462-f2c67632132b
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisInterlockedInsertTailList, NdisInterlockedInsertTailList macro [Network Drivers Starting with Windows Vista], ndis/NdisInterlockedInsertTailList, ndis_interlocked_ref_1fd860e3-2f63-41a0-9231-7e50a9b87e36.xml, netvista.ndisinterlockedinserttaillist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisInterlockedInsertTailList (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisInterlockedInsertTailList (NDIS 5.1)) in Windows XP.
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
-	NdisInterlockedInsertTailList
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisInterlockedInsertTailList macro


## -description


The 
  <b>NdisInterlockedInsertTailList</b> function inserts an entry, usually a packet, at the tail of a doubly
  linked list so that access to the list is synchronized in a multiprocessor-safe way.


## -parameters




### -param _ListHead [in]

A pointer to the head of the doubly linked list into which an entry is to be inserted.


### -param _ListEntry [in]

A pointer to the entry to be inserted at the end of the list.


### -param _SpinLock [in]

A pointer to a caller-supplied spin lock, used to synchronize access to the list.


## -remarks



Before calling 
    <b>NdisInterlockedInsertTailList</b>, a driver must initialize the variable at 
    <i>ListHead</i> with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562734">NdisInitializeListHead</a> function and
    the variable at 
    <i>SpinLock</i> with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561617">NdisAllocateSpinLock</a> function. The
    driver also must provide resident storage for these variables and for its internal queue.

The caller-supplied spin lock prevents any other function from accessing the driver's internal queue
    while 
    <b>NdisInterlockedInsertTailList</b> is inserting the given entry, even when the driver is running on a
    multiprocessor machine.

<b>NdisInterlockedInsertTailList</b> raises the IRQL to DISPATCH_LEVEL when it acquires the given spin
    lock and restores the original IRQL before it returns control. Consequently, any driver function that
    calls 
    <b>NdisInterlockedInsertTailList</b> cannot be pageable code.

To convert a returned value back to the address of the inserted entry, a driver can use the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff542043">CONTAINING_RECORD</a> macro.

If 
    <b>NdisInterlockedInsertTailList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for the 
    <i>ListHead</i> parameter and the list entries must be resident.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542043">CONTAINING_RECORD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561617">NdisAllocateSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562734">NdisInitializeListHead</a>



<a href="https://msdn.microsoft.com/c6221ce9-682c-453b-b036-f4219c9540da">
   NdisInterlockedInsertHeadList</a>



<a href="https://msdn.microsoft.com/85cbc158-7132-4666-8161-a78251a62e4d">
   NdisInterlockedRemoveHeadList</a>
 

 

