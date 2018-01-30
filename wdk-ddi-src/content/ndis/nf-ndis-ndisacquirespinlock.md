---
UID: NF:ndis.NdisAcquireSpinLock
title: NdisAcquireSpinLock macro
author: windows-driver-content
description: The NdisAcquireSpinLock function acquires a spin lock so the caller gains exclusive access to the resources, shared among driver functions, that the spin lock protects.
old-location: netvista\ndisacquirespinlock.htm
old-project: netvista
ms.assetid: c19c9396-bc24-4f4b-a0c9-f8de76a9c46b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisAcquireSpinLock, NdisAcquireSpinLock macro [Network Drivers Starting with Windows Vista], ndis/NdisAcquireSpinLock, ndis_spin_lock_ref_54c55d32-a190-4454-ad0d-670427754b8b.xml, netvista.ndisacquirespinlock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisAcquireSpinLock
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisAcquireSpinLock macro


## -description


The
  <b>NdisAcquireSpinLock</b> function acquires a spin lock so the caller gains exclusive access to the
  resources, shared among driver functions, that the spin lock protects.


## -syntax


````
VOID NdisAcquireSpinLock(
  [in] PNDIS_SPIN_LOCK SpinLock
);
````


## -parameters




### -param _SpinLock

TBD




#### - SpinLock [in]

Pointer to an opaque spin lock, already initialized by the caller.


## -remarks


The driver must initialize a variable of type NDIS_SPIN_LOCK with 
    <a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a> before it calls
    any other 
    <b>Ndis<i>Xxx</i>SpinLock</b> function. The driver must provide resident storage for the spin lock(s) it uses.

After acquiring a spin lock with 
    <b>NdisAcquireSpinLock</b>, the caller must release that lock with a call to 
    <a href="..\ndis\nf-ndis-ndisreleasespinlock.md">NdisReleaseSpinLock</a>. A driver must
    call 
    <b>NdisReleaseSpinLock</b> following each call to 
    <b>NdisAcquireSpinLock</b>. Otherwise, a deadlock occurs, hanging the driver.

A spin lock acquired with 
    <b>NdisAcquireSpinLock</b> must be released with 
    <b>NdisReleaseSpinLock</b>. A spin lock acquired with 
    <a href="..\ndis\nf-ndis-ndisdpracquirespinlock.md">NdisDprAcquireSpinLock</a> must be
    released with 
    <a href="..\ndis\nf-ndis-ndisdprreleasespinlock.md">NdisDprReleaseSpinLock</a>.

A driver should never hold a spin lock for an extended period (more than a few instructions). Holding
    a spin lock for longer than 25 microseconds degrades both system and driver performance.

A miniport driver cannot use a spin lock to protect resources that its other functions share with the 
    <a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> and/or 
    <mshelp:link keywords="netvista.miniportdisableinterruptex" tabindex="0"><i>
    MiniportDisableInterruptEx</i></mshelp:link> functions. Instead, a miniport driver must call 
    <b>NdisMSynchronizeWithInterruptEx</b> so that its 
    <mshelp:link keywords="netvista.miniportsynchronizeinterrupt" tabindex="0"><i>
    MiniportSynchronizeInterrupt</i></mshelp:link> function accesses such shared resources at the same DIRQL at which its
    
    <i>MiniportInterrupt</i> and/or 
    <i>MiniportDisableInterruptEx</i> functions do.

For more information about acquiring and releasing NDIS spin locks, see 
    <mshelp:link keywords="netvista.synchronization_and_notification_in_network_drivers" tabindex="0">Synchronization
    and Notification in Network Drivers</mshelp:link>.



## -see-also

<mshelp:link keywords="netvista.miniportsynchronizeinterrupt" tabindex="0"><i>
   MiniportSynchronizeInterrupt</i></mshelp:link>

<a href="..\ndis\nc-ndis-miniport_disable_interrupt.md">MiniportDisableInterruptEx</a>

<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a>

<a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nf-ndis-ndisdpracquirespinlock.md">NdisDprAcquireSpinLock</a>

<a href="..\ndis\nf-ndis-ndisreleasespinlock.md">NdisReleaseSpinLock</a>

<mshelp:link keywords="netvista.ndismsynchronizewithinterruptex" tabindex="0"><b>
   NdisMSynchronizeWithInterruptEx</b></mshelp:link>

<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAcquireSpinLock macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

