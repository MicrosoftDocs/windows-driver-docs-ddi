---
UID: NF:ndis.NdisInitializeReadWriteLock
title: NdisInitializeReadWriteLock function (ndis.h)
description: The NdisInitializeReadWriteLock function initializes a read or write lock variable of type NDIS_RW_LOCK.Note  The read-write lock interface is deprecated for NDIS 6.20 and later drivers, which should use NdisAllocateRWLock instead of NdisInitializeReadWriteLock.
old-location: netvista\ndisinitializereadwritelock.htm
tech.root: netvista
ms.assetid: 458d8a08-7212-4888-9bb3-07a470541c8d
ms.date: 05/02/2018
keywords: ["NdisInitializeReadWriteLock function"]
ms.keywords: NdisInitializeReadWriteLock, NdisInitializeReadWriteLock function [Network Drivers Starting with Windows Vista], ndis/NdisInitializeReadWriteLock, ndis_read_write_lock_ref_a74c25e4-58af-4fb0-9c5a-0fc29bad9aa7.xml, netvista.ndisinitializereadwritelock
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Deprecated for NDIS 6.20 and later drivers, which should use NdisAllocateRWLock instead of NdisInitializeReadWriteLock. Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisInitializeReadWriteLock   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisInitializeReadWriteLock   (NDIS 5.1)) in Windows XP.
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
req.dll: Ndis.sys
req.irql: Any level (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisInitializeReadWriteLock
 - ndis/NdisInitializeReadWriteLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - ndis.sys
api_name:
 - NdisInitializeReadWriteLock
---

# NdisInitializeReadWriteLock function


## -description

The
  <b>NdisInitializeReadWriteLock</b> function initializes a read or write lock variable of type 
  <b>NDIS_RW_LOCK</b>.
<div class="alert"><b>Note</b>  The read-write lock interface is deprecated for NDIS 6.20 and later drivers, which should use <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocaterwlock">NdisAllocateRWLock</a> instead of <b>NdisInitializeReadWriteLock</b>.</div><div> </div>

## -parameters

### -param Lock 

[out]
A pointer to an opaque 
     <b>NDIS_RW_LOCK</b> variable that represents a lock. The caller can use this lock to gain write or read
     access to resources that are shared among non-ISR driver threads.

## -remarks

An 
    <b>NDIS_RW_LOCK</b> variable is used to limit write access to shared resources to one non-ISR driver
    thread at a time. This 
    <b>NDIS_RW_LOCK</b> can allow multiple non-ISR driver threads concurrent read access to those resources.
    Such read access is not permitted during a write access.

The 
    <i>Lock</i> pointer that is passed to 
    <b>NdisInitializeReadWriteLock</b> is a required parameter for all other 
    <b>Ndis..ReadWriteLock</b> functions.

Before a driver calls the 
    <a href="/previous-versions/ff560696(v=vs.85)">NdisAcquireReadWriteLock</a> function
    to obtain write or read access to a resource, the driver must call 
    <b>NdisInitializeReadWriteLock</b> to initialize the lock that is associated with that resource. The
    caller must provide nonpaged storage for the variable at 
    <i>Lock</i> .

After calling 
    <b>NdisInitializeReadWriteLock</b>, the driver can call 
    <a href="/previous-versions/ff560696(v=vs.85)">NdisAcquireReadWriteLock</a> to obtain either write or read access to the resource. Only one non-ISR
    driver thread at a time can obtain write access to the resource. When one non-ISR thread has write
    access, all read and write accesses by other non-ISR threads must wait until the write-access holder
    releases the lock. However, if a non-ISR thread has read access, other non-ISR threads can concurrently
    acquire read access.

Initialize and use this type of lock for resources that are frequently accessed for reading and
    infrequently accessed for writing.

Once resource access is complete, the driver calls the 
    <a href="/previous-versions/ff564521(v=vs.85)">
    NdisReleaseReadWriteLock</a> function.

Each lock that a driver initializes does one of the following:

<ul>
<li>
Protects a discrete set of shared resources from simultaneous write and read access by driver
      threads that run at IRQL <= DISPATCH_LEVEL.

</li>
<li>
Exposes a discrete set of shared resources to simultaneous read access by driver threads that run at
      IRQL <= DISPATCH_LEVEL.

</li>
</ul>
Callers of 
    <b>NdisInitializeReadWriteLock</b> can run at any IRQL. Usually a caller is running at IRQL =
    PASSIVE_LEVEL during initialization.

## -see-also

<a href="/previous-versions/ff560696(v=vs.85)">NdisAcquireReadWriteLock</a>



<a href="/previous-versions/ff564521(v=vs.85)">NdisReleaseReadWriteLock</a>