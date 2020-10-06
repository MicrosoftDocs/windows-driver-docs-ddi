---
UID: NF:ndis.NdisInterlockedRemoveHeadList
title: NdisInterlockedRemoveHeadList macro (ndis.h)
description: The NdisInterlockedRemoveHeadList function removes an entry, usually a packet, from the head of a doubly linked list so that access to the list is synchronized in a multiprocessor-safe way.
old-location: netvista\ndisinterlockedremoveheadlist.htm
tech.root: netvista
ms.assetid: 85cbc158-7132-4666-8161-a78251a62e4d
ms.date: 05/02/2018
keywords: ["NdisInterlockedRemoveHeadList macro"]
ms.keywords: NdisInterlockedRemoveHeadList, NdisInterlockedRemoveHeadList macro [Network Drivers Starting with Windows Vista], ndis/NdisInterlockedRemoveHeadList, ndis_interlocked_ref_5aacd492-068c-4cfe-afa6-4e0e63cf66e9.xml, netvista.ndisinterlockedremoveheadlist
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisInterlockedRemoveHeadList
 - ndis/NdisInterlockedRemoveHeadList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisInterlockedRemoveHeadList
---

# NdisInterlockedRemoveHeadList macro


## -description

The 
  <b>NdisInterlockedRemoveHeadList</b> function removes an entry, usually a packet, from the head of a doubly
  linked list so that access to the list is synchronized in a multiprocessor-safe way.

## -parameters

### -param _ListHead 

[in]
A pointer to the head of the doubly linked list from which an entry is to be removed.

### -param _SpinLock 

[in]
A pointer to a caller-supplied spin lock, used to synchronize access to the list.

## -remarks

Before calling any 
    <b>NdisInterlocked..List</b> function, a driver must initialize the variable at 
    <i>ListHead</i> with the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinitializelisthead">NdisInitializeListHead</a> function and
    the variable at 
    <i>SpinLock</i> with the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a> function. The
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
    <a href="/windows-hardware/drivers/kernel/mm-bad-pointer">CONTAINING_RECORD</a> macro.

If 
    <b>NdisInterlockedRemoveHeadList</b> is called at IRQL >= DISPATCH_LEVEL, the storage for the 
    <i>ListHead</i> parameter must be resident.

## -see-also

<a href="/windows-hardware/drivers/kernel/mm-bad-pointer">CONTAINING_RECORD</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinitializelisthead">NdisInitializeListHead</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinterlockedinsertheadlist">
   NdisInterlockedInsertHeadList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinterlockedinserttaillist">
   NdisInterlockedInsertTailList</a>