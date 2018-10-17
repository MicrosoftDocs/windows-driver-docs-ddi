---
UID: NF:ndis.NdisDprReleaseSpinLock
title: NdisDprReleaseSpinLock macro
author: windows-driver-content
description: The NdisDprReleaseSpinLock function releases a spin lock acquired in the immediately preceding call to the NdisDprAcquireSpinLock function.
old-location: netvista\ndisdprreleasespinlock.htm
tech.root: netvista
ms.assetid: d6a7af70-6a1e-471b-919f-80a704d25446
ms.date: 5/2/2018
ms.keywords: NdisDprReleaseSpinLock, NdisDprReleaseSpinLock macro [Network Drivers Starting with Windows Vista], ndis/NdisDprReleaseSpinLock, ndis_spin_lock_ref_7f9e73b2-9284-4a8c-895e-209a7685fa94.xml, netvista.ndisdprreleasespinlock
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisDprReleaseSpinLock (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisDprReleaseSpinLock (NDIS   5.1)) in Windows XP.
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisDprReleaseSpinLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisDprReleaseSpinLock macro


## -description


The 
  <b>NdisDprReleaseSpinLock</b> function releases a spin lock acquired in the immediately preceding call to
  the 
  <a href="https://msdn.microsoft.com/2e21d2f8-467e-43d3-8261-2373a8b8daa4">
  NdisDprAcquireSpinLock</a> function.


## -parameters




### -param _SpinLock [in]

Pointer to the acquired spin lock to be released.


## -remarks



Release of the spin lock allows another driver function to use the resources the lock protects after
    that function acquires the spin lock.

A spin lock acquired with 
    <b>NdisDprAcquireSpinLock</b> must be released with 
    <b>NdisDprReleaseSpinLock</b>. A spin lock acquired with 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff560699">NdisAcquireSpinLock</a> must be released
    with 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564524">NdisReleaseSpinLock</a>.

For more information about acquiring and releasing NDIS spin locks, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronization-and-notification-in-network-drivers">Synchronization
    and Notification in Network Drivers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561749">NdisDprAcquireSpinLock</a>
 

 

