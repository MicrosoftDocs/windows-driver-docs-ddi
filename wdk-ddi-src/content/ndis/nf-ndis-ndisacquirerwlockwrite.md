---
UID: NF:ndis.NdisAcquireRWLockWrite
title: NdisAcquireRWLockWrite function (ndis.h)
description: The NdisAcquireRWLockWrite function obtains a write lock that the caller uses for write access to resources that are shared between driver threads.
old-location: netvista\ndisacquirerwlockwrite.htm
tech.root: netvista
ms.assetid: 124302d7-0776-4025-b71f-ce6300f97f49
ms.date: 05/02/2018
ms.keywords: NdisAcquireRWLockWrite, NdisAcquireRWLockWrite function [Network Drivers Starting with Windows Vista], ndis/NdisAcquireRWLockWrite, ndis_processor_group_ref_f957b48a-4c09-4348-897c-51813ede9b19.xml, netvista.ndisacquirerwlockwrite
ms.topic: function
f1_keywords:
 - "ndis/NdisAcquireRWLockWrite"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisAcquireRWLockWrite
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisAcquireRWLockWrite function


## -description


The 
  <b>NdisAcquireRWLockWrite</b> function obtains a write lock that the caller uses for write access to
  resources that are shared between driver threads.


## -parameters




### -param Lock [in]

A pointer to an opaque 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff567279(v=vs.85)">NDIS_RW_LOCK_EX</a> variable that represents a
     lock. The caller can use this lock to gain write or read access to resources that are shared between
     non-ISR driver threads.


### -param LockState [out]

A pointer to an opaque 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_lock_state_ex">LOCK_STATE_EX</a> variable that tracks the state
     of the lock. This variable exists in the interval between the times that the caller obtains and releases
     the lock. The caller must use a different variable of type <b>LOCK_STATE_EX</b> for each attempt that it makes to
     obtain the lock from the same non-ISR driver thread.


### -param Flags [in]

A <b>ULONG</b> value that contains lock flags. Set this parameter to <b>NDIS_RWL_AT_DISPATCH_LEVEL</b> if the
     caller's current IRQL is <b>DISPATCH_LEVEL</b>. Otherwise, set this parameter to zero. For more information
     about dispatch IRQL tracking, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/dispatch-irql-tracking">Dispatch IRQL Tracking</a>.

<div class="alert"><b>Note</b>  If the caller knows the current IRQL is <b>DISPATCH_LEVEL</b>, set this parameter to <b>NDIS_RWL_AT_DISPATCH_LEVEL</b>.  This flag makes the lock even more efficient by causing it to omit a check for the current IRQL.  If the current IRQL is unknown, do not test the current IRQL with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kegetcurrentirql">KeGetCurrentIrql</a> solely to determine whether to set this flag, as it is more efficient to allow the <b>NdisAcquireRWLockWrite</b> function to test the IRQL itself.</div>
<div> </div>

## -returns



None




## -remarks



NDIS drivers call the 
    <b>NdisAcquireRWLockWrite</b> function to modify resources that are shared between driver threads.

The driver must allocate a variable of type 
    <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff567279(v=vs.85)">NDIS_RW_LOCK_EX</a> with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocaterwlock">NdisAllocateRWLock</a> function before the
    driver calls the 
    <b>NdisAcquireRWLockWrite</b> function. The driver must provide a handle to 
    <b>NdisAllocateRWLock</b> for the resident storage for the locks it uses.

After the driver calls 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocaterwlock">NdisAllocateRWLock</a>, it can call 
    <b>NdisAcquireRWLockWrite</b> or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisacquirerwlockread">NdisAcquireRWLockRead</a> to obtain
    either write or read access to the resource. Only one non-ISR driver thread at a time can obtain write
    access to the resource. When one non-ISR thread has write access, all read and write accesses by other
    non-ISR threads must wait until the write-access holder releases the lock. However, if a non-ISR thread
    has read access, other non-ISR threads can concurrently obtain read access.

The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff567279(v=vs.85)">NDIS_RW_LOCK_EX</a> lock does not support promotion from read to write.  Once a processor has acquired an <b>NDIS_RW_LOCK_EX</b> for read access (by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisacquirerwlockread">NdisAcquireRWLockRead</a>), the same processor must not attempt to acquire write access (by calling <b>NdisAcquireRWLockWrite</b>) until the previous read access is released.

An <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff567279(v=vs.85)">NDIS_RW_LOCK_EX</a> write lock  can be acquired recursively on the same processor.  For each call to <b>NdisAcquireRWLockWrite</b>, there must be a corresponding call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisreleaserwlock">NdisReleaseRWLock</a>.  The lock is only released after the last call to <b>NdisReleaseRWLock</b>.

A driver thread should never hold a write lock for more than a few microseconds. Holding a write lock
    for a prolonged period of time degrades both operating system and driver performance.

The driver cannot use a lock to protect resources from read or write access that its other functions
    share with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a> or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_disable_interrupt">
    MiniportDisableInterruptEx</a> functions, or both. Instead, the driver must call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismsynchronizewithinterruptex">
    NdisMSynchronizeWithInterruptEx</a> so that its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_synchronize_interrupt">
    MiniportSynchronizeInterrupt</a> function accesses such shared resources at the same DIRQL that its 
    <i>MiniportInterrupt</i> or 
    <i>
    MiniportDisableInterruptEx</i> functions, or both, do.

<b>NdisAcquireRWLockWrite</b> raises the IRQL to <b>DISPATCH_LEVEL</b> by obtaining a spin lock.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_lock_state_ex">LOCK_STATE_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_disable_interrupt">MiniportDisableInterruptEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_synchronize_interrupt">
   MiniportSynchronizeInterrupt</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff567279(v=vs.85)">NDIS_RW_LOCK_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisacquirerwlockread">NdisAcquireRWLockRead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocaterwlock">NdisAllocateRWLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismsynchronizewithinterruptex">
   NdisMSynchronizeWithInterruptEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisreleaserwlock">NdisReleaseRWLock</a>
 

 

