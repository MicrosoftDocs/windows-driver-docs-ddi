---
UID: NF:ndis.NdisReleaseRWLock
title: NdisReleaseRWLock function (ndis.h)
description: The NdisReleaseRWLock function releases a read/write lock that the caller uses to gain access to resources that are shared between driver threads.
old-location: netvista\ndisreleaserwlock.htm
tech.root: netvista
ms.assetid: e0859f3f-0acc-45b7-99b2-ef420cd06565
ms.date: 05/02/2018
ms.keywords: NdisReleaseRWLock, NdisReleaseRWLock function [Network Drivers Starting with Windows Vista], ndis/NdisReleaseRWLock, ndis_processor_group_ref_bbc47204-3cf6-4154-bafc-23c14cff452b.xml, netvista.ndisreleaserwlock
ms.topic: function
f1_keywords:
 - "ndis/NdisReleaseRWLock"
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
- NdisReleaseRWLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisReleaseRWLock function


## -description


The 
  <b>NdisReleaseRWLock</b> function releases a read/write lock that the caller uses to gain access to
  resources that are shared between driver threads.


## -parameters




### -param Lock [in]

A pointer to an opaque 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff567279(v=vs.85)">NDIS_RW_LOCK_EX</a> variable that represents a
     lock. The caller can use this lock to gain write or read access to resources that are shared between
     non-ISR driver threads.


### -param LockState [in]

A pointer to an opaque 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_lock_state_ex">LOCK_STATE_EX</a> variable that tracks the state
     of the lock. This variable exists in the interval between the times that the caller obtains and releases
     the lock. The caller must use a different variable of type LOCK_STATE_EX for each attempt that it makes
     to obtain the lock from the same non-ISR driver thread.


## -returns



None




## -remarks



NDIS drivers call the 
    <b>NdisReleaseRWLock</b> function to release a read/write lock that was previously obtained by calling the    
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisacquirerwlockread">NdisAcquireRWLockRead</a> or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisacquirerwlockwrite">
    NdisAcquireRWLockWrite</a> function.

A driver must obtain a read/write lock before the driver can call 
    <b>NdisReleaseRWLock</b>. Each call to obtain a lock requires a reciprocal call to 
    <b>NdisReleaseRWLock</b>.

The acquisition of an <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff567279(v=vs.85)">NDIS_RW_LOCK_EX</a> is affinitized to the current processor.  Drivers must call <b>NdisReleaseRWLock</b> on the same processor that made the corresponding call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisacquirerwlockread">NdisAcquireRWLockRead</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisacquirerwlockwrite">NdisAcquireRWLockWrite</a>.

<b>NdisReleaseRWLock</b> restores the original IRQL that was used by its caller before the lock was
    obtained.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_lock_state_ex">LOCK_STATE_EX</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff567279(v=vs.85)">NDIS_RW_LOCK_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisacquirerwlockread">NdisAcquireRWLockRead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisacquirerwlockwrite">NdisAcquireRWLockWrite</a>
 

 

