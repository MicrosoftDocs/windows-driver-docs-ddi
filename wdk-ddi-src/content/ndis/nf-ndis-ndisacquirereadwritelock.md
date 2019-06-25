---
UID: NF:ndis.NdisAcquireReadWriteLock
title: NdisAcquireReadWriteLock function (ndis.h)
description: The NdisAcquireReadWriteLock function acquires a lock that the caller uses for either write or read access to the resources that are shared among driver threads.Note  The read-write lock interface is deprecated for NDIS 6.20 and later drivers, which should use NdisAcquireRWLockRead or NdisAcquireRWLockWrite instead of NdisAcquireReadWriteLock.
old-location: netvista\ndisacquirereadwritelock.htm
tech.root: netvista
ms.assetid: 563b4bff-36ee-4597-ae6e-7d3811592549
ms.date: 05/02/2018
ms.keywords: NdisAcquireReadWriteLock, NdisAcquireReadWriteLock function [Network Drivers Starting with Windows Vista], ndis/NdisAcquireReadWriteLock, ndis_read_write_lock_ref_6a27c811-da37-410d-8ca6-d982832b1d09.xml, netvista.ndisacquirereadwritelock
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Deprecated for NDIS 6.20 and later drivers, which should use NdisAcquireRWLockRead or NdisAcquireRWLockWrite instead. Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisAcquireReadWriteLock (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisAcquireReadWriteLock (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Synch_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: Ndis.sys
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- ndis.sys
api_name:
- NdisAcquireReadWriteLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisAcquireReadWriteLock function


## -description


The 
  <b>NdisAcquireReadWriteLock</b> function acquires a lock that the caller uses for either write or read
  access to the resources that are shared among driver threads.
<div class="alert"><b>Note</b>  The read-write lock interface is deprecated for NDIS 6.20 and later drivers, which should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisacquirerwlockread">NdisAcquireRWLockRead</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisacquirerwlockwrite">NdisAcquireRWLockWrite</a> instead of <b>NdisAcquireReadWriteLock</b>.</div><div> </div>

## -parameters




### -param Lock [in, out]

A pointer to an opaque variable that represents a lock. The caller can use this lock to access
     shared resources.


### -param fWrite [in]

A Boolean value. If the value is <b>TRUE</b>, this function is provided with write access to shared
     resources; if the value is <b>FALSE</b>, this function is provided with read access.


### -param _Requires_lock_not_held_

**LockState**. A pointer to an opaque variable that tracks the state of the lock. This variable exists in the
     interval between the time the caller acquires and releases the lock. The caller must use a different
     variable of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_lock_state">LOCK_STATE</a> for each attempt that it makes to acquire the lock from the same non-ISR
     driver thread.




## -returns



None




## -remarks



The driver must initialize a variable of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_rw_lock">NDIS_RW_LOCK</a> using the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisinitializereadwritelock">
    NdisInitializeReadWriteLock</a> function before the driver calls any other 
    Ndis<i>Xxx</i>ReadWriteLock function. The driver must provide resident storage for the locks it uses.

After acquiring a lock by using 
    <b>NdisAcquireReadWriteLock</b>, the caller must release that lock by calling the 
    <a href="https://msdn.microsoft.com/a910ae2d-8a3b-451c-b1f2-a19f7f9f14a2">
    NdisReleaseReadWriteLock</a> function. To decrement the reference count of the lock, a driver must call    
    <b>NdisReleaseReadWriteLock</b> once for each call to 
    <b>NdisAcquireReadWriteLock</b>.

To modify resources that are shared among driver threads, a driver thread must acquire a write lock.
    To simply monitor those resources, a driver thread must acquire a read-only lock. Read access does not
    require interlocked operations or contention for spin locks. Using read-only access helps to maintain
    good operating system and driver performance.

A driver thread should never hold a write lock for more than 25 microseconds. Holding a write lock for
    a prolonged period degrades both operating system and driver performance.

The driver cannot use a lock to protect resources from read or write access that its other functions
    share with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a> and/or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_disable_interrupt">
    MiniportDisableInterruptEx</a> functions. Instead, the driver must call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismsynchronizewithinterruptex">
    NdisMSynchronizeWithInterruptEx</a> so that its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_synchronize_interrupt">
    MiniportSynchronizeInterrupt</a> function accesses such shared resources at the same DIRQL at which its    
    <i>MiniportInterrupt</i> and/or 
    <i>
    MiniportDisableInterruptEx</i> functions do.

<b>NdisAcquireReadWriteLock</b> always raises the IRQL. For a write operation, 
    <b>NdisAcquireReadWriteLock</b> raises the IRQL by acquiring a spin lock. For a read operation, 
    <b>NdisAcquireReadWriteLock</b> explicitly raises the IRQL to IRQL = <b>DISPATCH_LEVEL</b>.

For more information about acquiring and releasing NDIS spin locks, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronization-and-notification-in-network-drivers">Synchronization
    and Notification in Network Drivers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_disable_interrupt">MiniportDisableInterruptEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_synchronize_interrupt">
   MiniportSynchronizeInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisacquirerwlockread">NdisAcquireRWLockRead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisacquirerwlockwrite">NdisAcquireRWLockWrite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisinitializereadwritelock">NdisInitializeReadWriteLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismsynchronizewithinterruptex">
   NdisMSynchronizeWithInterruptEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564521">NdisReleaseReadWriteLock</a>
 

 

