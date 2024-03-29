---
UID: NF:ndis.NdisFreeRWLock
title: NdisFreeRWLock function (ndis.h)
description: The NdisFreeRWLock function frees a read/write lock that was previously allocated with the NdisAllocateRWLock function.
old-location: netvista\ndisfreerwlock.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisFreeRWLock function"]
ms.keywords: NdisFreeRWLock, NdisFreeRWLock function [Network Drivers Starting with Windows Vista], ndis/NdisFreeRWLock, ndis_processor_group_ref_f711221a-f265-446e-86bc-7b5b4d17f7d9.xml, netvista.ndisfreerwlock
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisFreeRWLock
 - ndis/NdisFreeRWLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisFreeRWLock
---

# NdisFreeRWLock function


## -description

The 
  <b>NdisFreeRWLock</b> function frees a read/write lock that was previously allocated with the 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocaterwlock">NdisAllocateRWLock</a> function.

## -parameters

### -param Lock [in]


A pointer to an opaque 
     <a href="/previous-versions/windows/hardware/drivers/ff567279(v=vs.85)">NDIS_RW_LOCK_EX</a> variable that represents a
     lock. The caller can use this lock to gain write or read access to resources that are shared among
     non-ISR driver threads.

## -remarks

NDIS drivers call the 
    <b>NdisFreeRWLock</b> function to free the 
    <a href="/previous-versions/windows/hardware/drivers/ff567279(v=vs.85)">NDIS_RW_LOCK_EX</a> structure and any associated
    resources that were previously allocated with the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocaterwlock">NdisAllocateRWLock</a> function.

A driver must call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreleaserwlock">NdisReleaseRWLock</a> function to release a
    read/write lock before it calls the 
    <b>NdisFreeRWLock</b> function.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff567279(v=vs.85)">NDIS_RW_LOCK_EX</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocaterwlock">NdisAllocateRWLock</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreleaserwlock">NdisReleaseRWLock</a>
