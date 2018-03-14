---
UID: NF:ndis.NdisFreeSpinLock
title: NdisFreeSpinLock function
author: windows-driver-content
description: The NdisFreeSpinLock function releases a spin lock initialized in a preceding call to the NdisAllocateSpinLock functioin.
old-location: netvista\ndisfreespinlock.htm
old-project: netvista
ms.assetid: 4807d413-c40f-4ee8-b670-9afcac809bd2
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisFreeSpinLock, NdisFreeSpinLock function [Network Drivers Starting with Windows Vista], ndis/NdisFreeSpinLock, ndis_spin_lock_ref_c5b1dcb1-afdc-4622-a07b-f81bb7c1f550.xml, netvista.ndisfreespinlock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFreeSpinLock
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFreeSpinLock function


## -description


The 
  <b>NdisFreeSpinLock</b> function releases a spin lock initialized in a preceding call to the 
  <a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a> functioin.


## -syntax


````
VOID NdisFreeSpinLock(
  _In_ PNDIS_SPIN_LOCK SpinLock
);
````


## -parameters




### -param SpinLock [in]

Pointer to the spin lock to be deinitialized.


## -returns



None




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

<a href="..\ndis\nf-ndis-ndisdprreleasespinlock.md">NdisDprReleaseSpinLock</a>



<a href="..\ndis\nf-ndis-ndisinterlockedinsertheadlist.md">
   NdisInterlockedInsertHeadList</a>



<a href="..\ndis\nf-ndis-ndisinterlockedinserttaillist.md">
   NdisInterlockedInsertTailList</a>



<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>



<a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a>



<a href="..\ndis\nf-ndis-ndisinterlockedremoveheadlist.md">
   NdisInterlockedRemoveHeadList</a>



<a href="..\ndis\nf-ndis-ndisacquirespinlock.md">NdisAcquireSpinLock</a>



<a href="..\ndis\nf-ndis-ndisinterlockedaddulong.md">NdisInterlockedAddUlong</a>



<a href="..\ndis\nf-ndis-ndisreleasespinlock.md">NdisReleaseSpinLock</a>



<a href="..\ndis\nf-ndis-ndisdpracquirespinlock.md">NdisDprAcquireSpinLock</a>



 

 


