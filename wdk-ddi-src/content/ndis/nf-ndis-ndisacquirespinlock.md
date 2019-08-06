---
UID: NF:ndis.NdisAcquireSpinLock
title: NdisAcquireSpinLock macro (ndis.h)
description: The NdisAcquireSpinLock function acquires a spin lock so the caller gains exclusive access to the resources, shared among driver functions, that the spin lock protects.
old-location: netvista\ndisacquirespinlock.htm
tech.root: netvista
ms.assetid: c19c9396-bc24-4f4b-a0c9-f8de76a9c46b
ms.date: 05/02/2018
ms.keywords: NdisAcquireSpinLock, NdisAcquireSpinLock macro [Network Drivers Starting with Windows Vista], ndis/NdisAcquireSpinLock, ndis_spin_lock_ref_54c55d32-a190-4454-ad0d-670427754b8b.xml, netvista.ndisacquirespinlock
ms.topic: macro
f1_keywords:
 - "ndis/NdisAcquireSpinLock"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisAcquireSpinLock (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisAcquireSpinLock (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Synch_Function, SpinLock, SpinLockBalanced, SpinLockDpr, SpinLockDprRelease, SpinlockRelease
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
- NdisAcquireSpinLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisAcquireSpinLock macro


## -description


The
  <b>NdisAcquireSpinLock</b> function acquires a spin lock so the caller gains exclusive access to the
  resources, shared among driver functions, that the spin lock protects.


## -parameters




### -param _SpinLock [in]

Pointer to an opaque spin lock, already initialized by the caller.


## -remarks



The driver must initialize a variable of type NDIS_SPIN_LOCK with 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a> before it calls
    any other 
    <b>Ndis<i>Xxx</i>SpinLock</b> function. The driver must provide resident storage for the spin lock(s) it uses.

After acquiring a spin lock with 
    <b>NdisAcquireSpinLock</b>, the caller must release that lock with a call to 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisreleasespinlock">NdisReleaseSpinLock</a>. A driver must
    call 
    <b>NdisReleaseSpinLock</b> following each call to 
    <b>NdisAcquireSpinLock</b>. Otherwise, a deadlock occurs, hanging the driver.

A spin lock acquired with 
    <b>NdisAcquireSpinLock</b> must be released with 
    <b>NdisReleaseSpinLock</b>. A spin lock acquired with 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisdpracquirespinlock">NdisDprAcquireSpinLock</a> must be
    released with 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisdprreleasespinlock">NdisDprReleaseSpinLock</a>.

A driver should never hold a spin lock for an extended period (more than a few instructions). Holding
    a spin lock for longer than 25 microseconds degrades both system and driver performance.

A miniport driver cannot use a spin lock to protect resources that its other functions share with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a> and/or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_disable_interrupt">
    MiniportDisableInterruptEx</a> functions. Instead, a miniport driver must call 
    <b>NdisMSynchronizeWithInterruptEx</b> so that its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_synchronize_interrupt">
    MiniportSynchronizeInterrupt</a> function accesses such shared resources at the same DIRQL at which its    
    <i>MiniportInterrupt</i> and/or 
    <i>MiniportDisableInterruptEx</i> functions do.

For more information about acquiring and releasing NDIS spin locks, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronization-and-notification-in-network-drivers">Synchronization
    and Notification in Network Drivers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_disable_interrupt">MiniportDisableInterruptEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_synchronize_interrupt">
   MiniportSynchronizeInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisdpracquirespinlock">NdisDprAcquireSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismsynchronizewithinterruptex">
   NdisMSynchronizeWithInterruptEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisreleasespinlock">NdisReleaseSpinLock</a>
 

 

