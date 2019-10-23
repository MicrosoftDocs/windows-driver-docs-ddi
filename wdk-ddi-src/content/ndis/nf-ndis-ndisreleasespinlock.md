---
UID: NF:ndis.NdisReleaseSpinLock
title: NdisReleaseSpinLock macro (ndis.h)
description: The NdisReleaseSpinLock function releases a spin lock that was acquired in a preceding call to the NdisAcquireSpinLock function.
old-location: netvista\ndisreleasespinlock.htm
tech.root: netvista
ms.assetid: dd833373-2879-49f0-9b16-fddb2f7495c1
ms.date: 05/02/2018
ms.keywords: NdisReleaseSpinLock, NdisReleaseSpinLock macro [Network Drivers Starting with Windows Vista], ndis/NdisReleaseSpinLock, ndis_spin_lock_ref_a4e1c783-4682-401c-a198-fdc14cbfa383.xml, netvista.ndisreleasespinlock
ms.topic: macro
f1_keywords:
 - "ndis/NdisReleaseSpinLock"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisReleaseSpinLock (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisReleaseSpinLock (NDIS   5.1)) in Windows XP.
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
req.irql: DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisReleaseSpinLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisReleaseSpinLock macro


## -description


The 
  <b>NdisReleaseSpinLock</b> function releases a spin lock that was acquired in a preceding call to the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisacquirespinlock">NdisAcquireSpinLock</a> function.


## -parameters




### -param _SpinLock [in]

Pointer to the acquired spin lock to be released.


## -remarks



A driver must initialize its spin lock with 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a> before it calls
    any other 
    <b>Ndis..SpinLock</b> function to access the resources protected by that spin lock.

A driver must call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisacquirespinlock">NdisAcquireSpinLock</a> to acquire the
    spin lock before it can call 
    <b>NdisReleaseSpinLock</b>. Each call to 
    <b>NdisAcquireSpinLock</b> requires a reciprocal call to 
    <b>NdisReleaseSpinLock</b> before the driver can call 
    <b>NdisAcquireSpinLock</b> again.

<b>NdisReleaseSpinLock</b> restores the original IRQL at which its caller was running before the call to 
    <b>NdisAcquireSpinLock</b>.

Any spin lock acquired with 
    <b>NdisAcquireSpinLock</b> must be released with 
    <b>NdisReleaseSpinLock</b>. Any spin lock acquired with 
    <b>NdisDprAcquireSpinLock</b> must be released with 
    <b>NdisDprReleaseSpinLock</b>.

For more information about acquiring and releasing NDIS spin locks, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronization-and-notification-in-network-drivers">Synchronization
    and Notification in Network Drivers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisacquirespinlock">NdisAcquireSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisdpracquirespinlock">NdisDprAcquireSpinLock</a>
 

 

