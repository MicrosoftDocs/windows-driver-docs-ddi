---
UID: NF:ndis.NdisDprReleaseReadWriteLock
title: NdisDprReleaseReadWriteLock function (ndis.h)
description: The NdisDprReleaseReadWriteLock function releases a lock that was acquired in a preceding call to NdisDprAcquireReadWriteLock.Note  The read-write lock interface is deprecated for NDIS 6.20 and later drivers, which should use NdisReleaseRWLock instead of NdisDprReleaseReadWriteLock.
old-location: netvista\ndisdprreleasereadwritelock.htm
tech.root: netvista
ms.assetid: BD9B13A7-5F5F-437a-BEB7-56DE6D03A29B
ms.date: 03/26/2018
ms.keywords: NdisDprReleaseReadWriteLock, NdisDprReleaseReadWriteLock function [Network Drivers Starting with Windows Vista], ndis/NdisDprReleaseReadWriteLock, netvista.ndisdprreleasereadwritelock
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and 6.1.
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
- NdisDprReleaseReadWriteLock
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisDprReleaseReadWriteLock function


## -description


The
  <a href="https://msdn.microsoft.com/library/windows/hardware/hh205389">NdisDprReleaseReadWriteLock</a> function releases a lock that was acquired in a preceding call to
  <a href="https://msdn.microsoft.com/library/windows/hardware/hh205388">NdisDprAcquireReadWriteLock</a>.
<div class="alert"><b>Note</b>  The read-write lock interface is deprecated for NDIS 6.20 and later drivers, which should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff564523">NdisReleaseRWLock</a> instead of <a href="https://msdn.microsoft.com/library/windows/hardware/hh205389">NdisDprReleaseReadWriteLock</a>.</div><div> </div>

## -parameters




### -param Lock [in, out]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff567277">NDIS_RW_LOCK</a> variable for the acquired lock to be released.


### -param LockState

A pointer to an opaque <a href="https://msdn.microsoft.com/library/windows/hardware/ff557067">LOCK_STATE</a> variable that tracks the state of the lock. This variable exists
     in the interval between the time the caller acquires and releases the lock.

## -returns



None




## -remarks



A driver must initialize a lock before calling any other
    Ndis<i>Xxx</i>ReadWriteLock function that is used to acquire or release read or write access to the
    resources that are protected by that lock. The
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562738">NdisInitializeReadWriteLock</a> function is used to initialize a lock.

A driver must call the
    <a href="https://msdn.microsoft.com/library/windows/hardware/hh205388">NdisDprAcquireReadWriteLock</a> function
    to acquire a lock before the driver can call
    <a href="https://msdn.microsoft.com/library/windows/hardware/hh205389">NdisDprReleaseReadWriteLock</a>. Each call to
    <b>NdisDprAcquireReadWriteLock</b> requires a reciprocal call to
    <b>NdisDprReleaseReadWriteLock</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh205388">NdisDprAcquireReadWriteLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562738">NdisInitializeReadWriteLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564523">NdisReleaseRWLock</a>
 

 

