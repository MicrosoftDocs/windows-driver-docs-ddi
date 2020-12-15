---
UID: NF:ndis.NdisFreeSpinLock
title: NdisFreeSpinLock function (ndis.h)
description: The NdisFreeSpinLock function releases a spin lock initialized in a preceding call to the NdisAllocateSpinLock functioin.
old-location: netvista\ndisfreespinlock.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisFreeSpinLock function"]
ms.keywords: NdisFreeSpinLock, NdisFreeSpinLock function [Network Drivers Starting with Windows Vista], ndis/NdisFreeSpinLock, ndis_spin_lock_ref_c5b1dcb1-afdc-4622-a07b-f81bb7c1f550.xml, netvista.ndisfreespinlock
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisFreeSpinLock (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisFreeSpinLock (NDIS 5.1)) in   Windows XP.
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
req.irql: Any level (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisFreeSpinLock
 - ndis/NdisFreeSpinLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisFreeSpinLock
---

# NdisFreeSpinLock function


## -description

The 
  <b>NdisFreeSpinLock</b> function releases a spin lock initialized in a preceding call to the 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a> functioin.

## -parameters

### -param SpinLock 

[in]
Pointer to the spin lock to be deinitialized.

## -remarks

If the caller of 
    <b>NdisFreeSpinLock</b> needs to use the spin lock again, it must call 
    <b>NdisAllocateSpinLock</b> before passing that spin lock pointer to any of the 
    <b>Ndis..SpinLock</b> or 
    <b>NdisInterlocked<i>Xxx</i></b> functions.

Callers of 
    <b>NdisFreeSpinLock</b> can run at any IRQL. Usually, this function is not called until a driver is
    unloading.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisacquirespinlock">NdisAcquireSpinLock</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisdpracquirespinlock">NdisDprAcquireSpinLock</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisdprreleasespinlock">NdisDprReleaseSpinLock</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinterlockedaddulong">NdisInterlockedAddUlong</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinterlockedinsertheadlist">
   NdisInterlockedInsertHeadList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinterlockedinserttaillist">
   NdisInterlockedInsertTailList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinterlockedremoveheadlist">
   NdisInterlockedRemoveHeadList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreleasespinlock">NdisReleaseSpinLock</a>
