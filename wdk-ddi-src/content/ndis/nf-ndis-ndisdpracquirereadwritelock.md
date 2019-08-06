---
UID: NF:ndis.NdisDprAcquireReadWriteLock
title: NdisDprAcquireReadWriteLock function (ndis.h)
description: The NdisDprAcquireReadWriteLock function acquires a lock that the caller uses for either write or read access to the resources that are shared among driver threads.Note  The read-write lock interface is deprecated for NDIS 6.20 and later drivers, which should use NdisAcquireRWLockRead or NdisAcquireRWLockWrite (setting NDIS_RWL_AT_DISPATCH_LEVEL in the Flags parameter) instead of NdisDprAcquireReadWriteLock.
old-location: netvista\ndisdpracquirereadwritelock.htm
tech.root: netvista
ms.assetid: 09B574FA-BCBA-4370-8F9F-BF30CE0BE52D
ms.date: 05/02/2018
ms.keywords: NdisDprAcquireReadWriteLock, NdisDprAcquireReadWriteLock function [Network Drivers Starting with Windows Vista], ndis/NdisDprAcquireReadWriteLock, netvista.ndisdpracquirereadwritelock
ms.topic: function
f1_keywords:
 - "ndis/NdisDprAcquireReadWriteLock"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Deprecated for NDIS 6.20 and later drivers, which should use NdisAcquireRWLockRead or NdisAcquireRWLockWrite instead of NdisDprAcquireReadWriteLock. Supported in NDIS 6.0 and 6.1.
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
req.irql: = DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisDprAcquireReadWriteLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisDprAcquireReadWriteLock function


## -description


The 
  <a href="https://msdn.microsoft.com/library/windows/hardware/hh205388">NdisDprAcquireReadWriteLock</a> function acquires a lock that the caller uses for either write or read
  access to the resources that are shared among driver threads.
<div class="alert"><b>Note</b>  The read-write lock interface is deprecated for NDIS 6.20 and later drivers, which should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisacquirerwlockread">NdisAcquireRWLockRead</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisacquirerwlockwrite">NdisAcquireRWLockWrite</a> (setting <b>NDIS_RWL_AT_DISPATCH_LEVEL</b> in the <i>Flags</i> parameter) instead of <a href="https://msdn.microsoft.com/library/windows/hardware/hh205388">NdisDprAcquireReadWriteLock</a>.</div><div> </div>

## -parameters




### -param Lock [in, out]

A pointer to an opaque variable that represents a lock. The caller can use this lock to access
     shared resources.


### -param fWrite [in]

A Boolean value. If the value is TRUE, this function is provided with write access to shared
     resources; if the value is FALSE, this function is provided with read access.


### -param LockState [out]

A pointer to an opaque variable that tracks the state of the lock. This variable exists in the
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
    <a href="https://msdn.microsoft.com/library/windows/hardware/hh205388">NdisDprAcquireReadWriteLock</a>, the caller must release that lock by calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/hh205389">NdisDprReleaseReadWriteLock</a> function. To decrement the reference count of the lock, a driver must call    
    <b>NdisDprReleaseReadWriteLock</b> once for each call to 
    <b>NdisDprAcquireReadWriteLock</b>.

It is safe to use both <a href="https://msdn.microsoft.com/library/windows/hardware/hh205388">NdisDprAcquireReadWriteLock</a> and <b>NdisDprAcquireReadWriteLock</b> on the same lock.  However, calls must be balanced so that if the lock is acquired with <b>NdisDprAcquireReadWriteLock</b>, it must be released with <a href="https://msdn.microsoft.com/library/windows/hardware/hh205389">NdisDprReleaseReadWriteLock</a>.  Likewise, if the lock is acquired with <b>NdisAcquireReadWriteLock</b>, it must be released with <b>NdisReleaseReadWriteLock</b>.

With some architectures, <a href="https://msdn.microsoft.com/library/windows/hardware/hh205388">NdisDprAcquireReadWriteLock</a>     performs faster than <b>NdisAcquireReadWriteLock</b>.  Drivers can use <b>NdisDprAcquireReadWriteLock</b>  rather than  <b>NdisAcquireReadWriteLock</b> when it is certain that the current IRQL is already <b>DISPATCH_LEVEL</b>.  However, it is not required.  The overhead of calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kegetcurrentirql">KeGetCurrentIrql</a> function is greater than the performance advantage of calling <b>NdisDprAcquireReadWriteLock</b> rather than <b>NdisAcquireReadWriteLock</b>.

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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismsynchronizewithinterruptex">NdisMSynchronizeWithInterruptEx</a> so that its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_synchronize_interrupt">
    MiniportSynchronizeInterrupt</a> function accesses such shared resources at the same DIRQL at which its    
    <i>MiniportInterrupt</i> and/or 
    <i>
    MiniportDisableInterruptEx</i> functions do.

For more information about acquiring and releasing NDIS spin locks, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronization-and-notification-in-network-drivers">Synchronization
    and Notification in Network Drivers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_lock_state">LOCK_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_disable_interrupt">MiniportDisableInterruptEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_synchronize_interrupt">
   MiniportSynchronizeInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisacquirerwlockread">NdisAcquireRWLockRead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisacquirerwlockwrite">NdisAcquireRWLockWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh205389">NdisDprReleaseReadWriteLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisinitializereadwritelock">NdisInitializeReadWriteLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismsynchronizewithinterruptex">
   NdisMSynchronizeWithInterruptEx</a>
 

 

