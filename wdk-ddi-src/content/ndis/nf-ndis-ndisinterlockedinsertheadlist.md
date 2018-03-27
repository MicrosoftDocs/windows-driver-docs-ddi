---
UID: NF:ndis.NdisInterlockedInsertHeadList
title: NdisInterlockedInsertHeadList macro
author: windows-driver-content
description: The NdisInterlockedInsertHeadList function inserts an entry, usually a packet, at the head of a doubly linked list so that access to the list is synchronized in a multiprocessor-safe way.
old-location: netvista\ndisinterlockedinsertheadlist.htm
old-project: netvista
ms.assetid: c6221ce9-682c-453b-b036-f4219c9540da
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisInterlockedInsertHeadList, NdisInterlockedInsertHeadList macro [Network Drivers Starting with Windows Vista], ndis/NdisInterlockedInsertHeadList, ndis_interlocked_ref_14cc728a-07b7-471f-a222-4810d9d79d5a.xml, netvista.ndisinterlockedinsertheadlist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisInterlockedInsertHeadList (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisInterlockedInsertHeadList (NDIS 5.1)) in Windows XP.
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
-	NdisInterlockedInsertHeadList
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisInterlockedInsertHeadList macro


## -description


The
  <b>NdisInterlockedInsertHeadList</b> function inserts an entry, usually a packet, at the head of a doubly
  linked list so that access to the list is synchronized in a multiprocessor-safe way.


## -parameters




### -param _ListHead [in]

A pointer to the head of the doubly linked list into which an entry is to be inserted.


### -param _ListEntry [in]

A pointer to the entry to be inserted at the head of the list.


### -param _SpinLock [in]

A pointer to a caller-supplied spin lock, used to synchronize access to the list.


## -remarks



Before calling 
    <b>NdisInterlockedInsertHeadList</b>, a driver must initialize the variable at 
    <i>ListHead</i> with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562734">NdisInitializeListHead</a> function and
    the variable at 
    <i>SpinLock</i> with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561617">NdisAllocateSpinLock</a> function. The
    driver also must provide resident storage for these variables and for its internal queue.

The caller-supplied spin lock prevents any other function from accessing the driver's internal queue
    while 
    <b>NdisInterlockedInsertHeadList</b> is inserting the given entry, even when the driver is running on a
    multiprocessor computer.

<b>NdisInterlockedInsertHeadList</b> raises IRQL to DISPATCH_LEVEL when it acquires the given spin lock
    and restores the original IRQL before it returns control. Consequently, any driver function that calls 
    <b>NdisInterlockedInsertHeadList</b> cannot be pageable code.

Most NDIS drivers process packets in FIFO order, so any driver that uses an interlocked queue tends to
    cal thel 
    <a href="https://msdn.microsoft.com/cc455bb1-3574-4dfb-9462-f2c67632132b">
    NdisInterlockedInsertTailList</a> function far more frequently than 
    <b>NdisInterlockedInsertHeadList</b>. Such a driver usually calls 
    <b>NdisInterlockedInsertHeadList</b> only to requeue a packet for a retry operation.

To convert a returned value back to the address of the inserted entry, a driver can use the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff542043">CONTAINING_RECORD</a> macro.

If 
    <b>NdisInterlockedInsertHeadList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for the 
    <i>ListHead</i> parameter and the list entries must be resident.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542043">CONTAINING_RECORD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561617">NdisAllocateSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562734">NdisInitializeListHead</a>



<a href="https://msdn.microsoft.com/cc455bb1-3574-4dfb-9462-f2c67632132b">
   NdisInterlockedInsertTailList</a>



<a href="https://msdn.microsoft.com/85cbc158-7132-4666-8161-a78251a62e4d">
   NdisInterlockedRemoveHeadList</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisInterlockedInsertHeadList macro%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

