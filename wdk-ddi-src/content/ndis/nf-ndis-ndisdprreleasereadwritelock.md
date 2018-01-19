---
UID: NF:ndis.NdisDprReleaseReadWriteLock
title: NdisDprReleaseReadWriteLock function
author: windows-driver-content
description: The NdisDprReleaseReadWriteLock function releases a lock that was acquired in a preceding call to NdisDprAcquireReadWriteLock.Note  The read-write lock interface is deprecated for NDIS 6.20 and later drivers, which should use NdisReleaseRWLock instead of NdisDprReleaseReadWriteLock.
old-location: netvista\ndisdprreleasereadwritelock.htm
old-project: netvista
ms.assetid: BD9B13A7-5F5F-437a-BEB7-56DE6D03A29B
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisDprReleaseReadWriteLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and 6.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisDprReleaseReadWriteLock
req.alt-loc: ndis.lib,ndis.dll
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
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisDprReleaseReadWriteLock function



## -description
The 
  <a href="..\ndis\nf-ndis-ndisreleasereadwritelock.md">NdisDprReleaseReadWriteLock</a> function releases a lock that was acquired in a preceding call to 
  <a href="..\ndis\nf-ndis-ndisacquirereadwritelock.md">NdisDprAcquireReadWriteLock</a>.



## -syntax

````
VOID NdisDprReleaseReadWriteLock(
  _Inout_ PNDIS_RW_LOCK Lock,
  _In_    PLOCK_STATE   LockState
);
````


## -parameters

### -param Lock [in, out]

A pointer to an <a href="..\ndis\ns-ndis-_ndis_rw_lock.md">NDIS_RW_LOCK</a> variable for the acquired lock to be released.


### -param LockState [in]

A pointer to an opaque <a href="..\ndis\ns-ndis-_lock_state.md">LOCK_STATE</a> variable that tracks the state of the lock. This variable exists
     in the interval between the time the caller acquires and releases the lock.


## -returns
None


## -remarks
A driver must initialize a lock before calling any other 
    Ndis<i>Xxx</i>ReadWriteLock function that is used to acquire or release read or write access to the
    resources that are protected by that lock. The 
    <a href="..\ndis\nf-ndis-ndisinitializereadwritelock.md">NdisInitializeReadWriteLock</a> function is used to initialize a lock.

A driver must call the 
    <a href="..\ndis\nf-ndis-ndisacquirereadwritelock.md">NdisDprAcquireReadWriteLock</a> function
    to acquire a lock before the driver can call 
    <a href="..\ndis\nf-ndis-ndisreleasereadwritelock.md">NdisDprReleaseReadWriteLock</a>. Each call to 
    <b>NdisDprAcquireReadWriteLock</b> requires a reciprocal call to 
    <b>NdisDprReleaseReadWriteLock</b>.


## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndisacquirereadwritelock.md">NdisDprAcquireReadWriteLock</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisinitializereadwritelock.md">NdisInitializeReadWriteLock</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisreleaserwlock.md">NdisReleaseRWLock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisDprReleaseReadWriteLock function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

