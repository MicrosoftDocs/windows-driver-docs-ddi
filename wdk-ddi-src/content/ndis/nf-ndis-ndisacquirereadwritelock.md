---
UID: NF:ndis.NdisAcquireReadWriteLock
title: NdisAcquireReadWriteLock function
author: windows-driver-content
description: The NdisAcquireReadWriteLock function acquires a lock that the caller uses for either write or read access to the resources that are shared among driver threads.Note  The read-write lock interface is deprecated for NDIS 6.20 and later drivers, which should use NdisAcquireRWLockRead or NdisAcquireRWLockWrite instead of NdisAcquireReadWriteLock.
old-location: netvista\ndisacquirereadwritelock.htm
old-project: netvista
ms.assetid: 563b4bff-36ee-4597-ae6e-7d3811592549
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisAcquireReadWriteLock, NdisAcquireReadWriteLock function [Network Drivers Starting with Windows Vista], ndis/NdisAcquireReadWriteLock, ndis_read_write_lock_ref_6a27c811-da37-410d-8ca6-d982832b1d09.xml, netvista.ndisacquirereadwritelock
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	ndis.sys
api_name:
-	NdisAcquireReadWriteLock
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisAcquireReadWriteLock function


## -description


The 
  <b>NdisAcquireReadWriteLock</b> function acquires a lock that the caller uses for either write or read
  access to the resources that are shared among driver threads.
<div class="alert"><b>Note</b>  The read-write lock interface is deprecated for NDIS 6.20 and later drivers, which should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff560697">NdisAcquireRWLockRead</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff560698">NdisAcquireRWLockWrite</a> instead of <b>NdisAcquireReadWriteLock</b>.</div><div> </div>

## -parameters




### -param Lock [in, out]

A pointer to an opaque variable that represents a lock. The caller can use this lock to access
     shared resources.


### -param fWrite [in]

A Boolean value. If the value is <b>TRUE</b>, this function is provided with write access to shared
     resources; if the value is <b>FALSE</b>, this function is provided with read access.


### -param _Requires_lock_not_held_

TBD




#### - LockState [out]

A pointer to an opaque variable that tracks the state of the lock. This variable exists in the
     interval between the time the caller acquires and releases the lock. The caller must use a different
     variable of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557067">LOCK_STATE</a> for each attempt that it makes to acquire the lock from the same non-ISR
     driver thread.


## -returns



None




## -remarks



The driver must initialize a variable of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff567277">NDIS_RW_LOCK</a> using the 
    <a href="https://msdn.microsoft.com/458d8a08-7212-4888-9bb3-07a470541c8d">
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
    <a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a> and/or 
    <a href="https://msdn.microsoft.com/6016ab15-56c6-4430-8883-d4cdcdf6116f">
    MiniportDisableInterruptEx</a> functions. Instead, the driver must call 
    <a href="https://msdn.microsoft.com/5dca9258-a3ae-43f4-a5aa-d591165d72ed">
    NdisMSynchronizeWithInterruptEx</a> so that its 
    <a href="https://msdn.microsoft.com/aac1ff91-76aa-46a0-8e8a-85b9f8c3323c">
    MiniportSynchronizeInterrupt</a> function accesses such shared resources at the same DIRQL at which its
    
    <i>MiniportInterrupt</i> and/or 
    <i>
    MiniportDisableInterruptEx</i> functions do.

<b>NdisAcquireReadWriteLock</b> always raises the IRQL. For a write operation, 
    <b>NdisAcquireReadWriteLock</b> raises the IRQL by acquiring a spin lock. For a read operation, 
    <b>NdisAcquireReadWriteLock</b> explicitly raises the IRQL to IRQL = <b>DISPATCH_LEVEL</b>.

For more information about acquiring and releasing NDIS spin locks, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/synchronization-and-notification-in-network-drivers">Synchronization
    and Notification in Network Drivers</a>.




## -see-also




<a href="https://msdn.microsoft.com/6016ab15-56c6-4430-8883-d4cdcdf6116f">MiniportDisableInterruptEx</a>



<a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a>



<a href="https://msdn.microsoft.com/aac1ff91-76aa-46a0-8e8a-85b9f8c3323c">
   MiniportSynchronizeInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560697">NdisAcquireRWLockRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560698">NdisAcquireRWLockWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562738">NdisInitializeReadWriteLock</a>



<a href="https://msdn.microsoft.com/5dca9258-a3ae-43f4-a5aa-d591165d72ed">
   NdisMSynchronizeWithInterruptEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564521">NdisReleaseReadWriteLock</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAcquireReadWriteLock function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
