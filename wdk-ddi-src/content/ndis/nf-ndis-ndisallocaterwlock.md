---
UID: NF:ndis.NdisAllocateRWLock
title: NdisAllocateRWLock function (ndis.h)
description: The NdisAllocateRWLock function allocates a read/write lock variable of type NDIS_RW_LOCK_EX.
old-location: netvista\ndisallocaterwlock.htm
tech.root: netvista
ms.assetid: 460c81bf-ae06-40f7-a019-b006e5c9f94b
ms.date: 05/02/2018
ms.keywords: NdisAllocateRWLock, NdisAllocateRWLock function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateRWLock, ndis_processor_group_ref_7df54f29-88d4-4596-9649-8af7b84f6d7e.xml, netvista.ndisallocaterwlock
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisAllocateRWLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisAllocateRWLock function


## -description


The 
  <b>NdisAllocateRWLock</b> function allocates a read/write lock variable of type 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a>.


## -parameters




### -param NdisHandle

A handle returned from one of the following functions:
     

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563654">NdisMRegisterMiniportDriver</a>  
<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>  
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564520">NdisRegisterProtocolDriver</a>  
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>  
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>  
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_attach">FilterAttach</a>  
<b>Windows 8 and Windows Server 2012 and later:  </b>If the read/write lock is being allocated in <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> before any NDIS handle is available, the caller may pass a NULL value for this parameter.


## -returns



<b>NdisAllocateRWLock</b> returns a pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> structure if one can be allocated; otherwise it returns <b>NULL</b>.




## -remarks



NDIS drivers call the 
    <b>NdisAllocateRWLock</b> function to allocate an 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> structure that controls
    read/write access to resources that are shared among driver threads. Drivers use a read/write lock for
    resources that are frequently accessed for reading and infrequently accessed for writing.

Each lock that a driver allocates can do one of the following:

<ul>
<li>
Protect a discrete set of shared resources from concurrent write and read access by driver threads
      that run at IRQL <= DISPATCH_LEVEL.

</li>
<li>
Expose a discrete set of shared resources to concurrent read access by driver threads that run at
      IRQL <= DISPATCH_LEVEL.

</li>
</ul>
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> pointer that 
    <b>NdisAllocateRWLock</b> returns is a required parameter for all other read/write lock functions.

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> is not fair.  That is, a processor waiting to acquire the lock for exclusive access may be starved by processors that hold the lock for read access.  Therefore, do not use an <b>NDIS_RW_LOCK_EX</b> in situations where the majority of accesses will be for write access.  If the majority of accesses will need write access, it is more efficient to simply use a kernel spin lock. For more information about spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548114">Introduction to Spin Locks</a>.

In situations where there are many acquisitions for read access on more than one processor, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> typically performs better than a kernel spin lock.  Use <b>NDIS_RW_LOCK_EX</b> when you expect many read accesses per second distributed across more than one processor.

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> structure defines attributes that limit write access to shared resources to one
    non-ISR driver thread at a time. The <b>NDIS_RW_LOCK_EX</b> structure can allow multiple non-ISR driver threads
    to have concurrent read access to the associated resources. Such read access is not permitted during a
    write access.

To modify the protected resources, a driver thread must obtain a write lock with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff560698">NdisAcquireRWLockWrite</a> function. To
    simply read those resources, a driver thread must obtain a read-only lock with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff560697">NdisAcquireRWLockRead</a> function. Read
    access does not require interlocked operations or contention for spin locks. Read-only access helps
    maintain good operating system and driver performance.

After the resource access is complete, the driver calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564523">NdisReleaseRWLock</a> function.

A driver must call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562598">NdisFreeRWLock</a> function to free the
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> structure that it allocated with the 
    <b>NdisAllocateRWLock</b> function.

You can use the <b>!ndiskd.ndisrwlock</b> debugger extension to inspect an <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a>, see how many readers it has, and see who its current writer is. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552270">NDIS Extensions (Ndiskd.dll)</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548114">Introduction to Spin Locks</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552270">NDIS Extensions (Ndiskd.dll)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560697">NdisAcquireRWLockRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560698">NdisAcquireRWLockWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562598">NdisFreeRWLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563654">NdisMRegisterMiniportDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564520">NdisRegisterProtocolDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564523">NdisReleaseRWLock</a>
 

 

