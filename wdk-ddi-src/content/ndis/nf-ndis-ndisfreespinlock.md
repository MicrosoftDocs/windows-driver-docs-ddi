---
UID: NF:ndis.NdisFreeSpinLock
title: NdisFreeSpinLock function
author: windows-driver-content
description: The NdisFreeSpinLock function releases a spin lock initialized in a preceding call to the NdisAllocateSpinLock functioin.
old-location: netvista\ndisfreespinlock.htm
tech.root: netvista
ms.assetid: 4807d413-c40f-4ee8-b670-9afcac809bd2
ms.date: 5/2/2018
ms.keywords: NdisFreeSpinLock, NdisFreeSpinLock function [Network Drivers Starting with Windows Vista], ndis/NdisFreeSpinLock, ndis_spin_lock_ref_c5b1dcb1-afdc-4622-a07b-f81bb7c1f550.xml, netvista.ndisfreespinlock
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFreeSpinLock function


## -description


The 
  <b>NdisFreeSpinLock</b> function releases a spin lock initialized in a preceding call to the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff561617">NdisAllocateSpinLock</a> functioin.


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




<a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560699">NdisAcquireSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561617">NdisAllocateSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561749">NdisDprAcquireSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561753">NdisDprReleaseSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562750">NdisInterlockedAddUlong</a>



<a href="https://msdn.microsoft.com/c6221ce9-682c-453b-b036-f4219c9540da">
   NdisInterlockedInsertHeadList</a>



<a href="https://msdn.microsoft.com/cc455bb1-3574-4dfb-9462-f2c67632132b">
   NdisInterlockedInsertTailList</a>



<a href="https://msdn.microsoft.com/85cbc158-7132-4666-8161-a78251a62e4d">
   NdisInterlockedRemoveHeadList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564524">NdisReleaseSpinLock</a>
 

 

