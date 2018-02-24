---
UID: NF:ndis.NdisReleaseReadWriteLock
title: NdisReleaseReadWriteLock function
author: windows-driver-content
description: The NdisReleaseReadWriteLock function releases a lock that was acquired in a preceding call to NdisAcquireReadWriteLock.Note  The read-write lock interface is deprecated for NDIS 6.20 and later drivers, which should use NdisReleaseRWLock instead of NdisReleaseReadWriteLock.
old-location: netvista\ndisreleasereadwritelock.htm
old-project: netvista
ms.assetid: a910ae2d-8a3b-451c-b1f2-a19f7f9f14a2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisReleaseReadWriteLock, ndis/NdisReleaseReadWriteLock, netvista.ndisreleasereadwritelock, NdisReleaseReadWriteLock function [Network Drivers Starting with Windows Vista], ndis_read_write_lock_ref_4f0f9891-a4a6-457d-b547-4f5543fbc534.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Deprecated for NDIS 6.20 and later drivers, which should use NdisReleaseRWLock instead of NdisReleaseReadWriteLock. Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisReleaseReadWriteLock (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisReleaseReadWriteLock (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Synch_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: Ndis.sys
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	ndis.sys
apiname:
-	NdisReleaseReadWriteLock
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisReleaseReadWriteLock function


## -description


The 
  <b>NdisReleaseReadWriteLock</b> function releases a lock that was acquired in a preceding call to 
  <a href="..\ndis\nf-ndis-ndisacquirereadwritelock.md">NdisAcquireReadWriteLock</a>.
<div class="alert"><b>Note</b>  The read-write lock interface is deprecated for NDIS 6.20 and later drivers, which should use <a href="..\ndis\nf-ndis-ndisreleaserwlock.md">NdisReleaseRWLock</a> instead of <b>NdisReleaseReadWriteLock</b>.</div><div> </div>

## -syntax


````
VOID NdisReleaseReadWriteLock(
  _Inout_ PNDIS_RW_LOCK Lock,
  _In_    PLOCK_STATE   LockState
);
````


## -parameters




### -param Lock [in, out]

A pointer to an <a href="..\ndis\ns-ndis-_ndis_rw_lock.md">NDIS_RW_LOCK</a> variable for the acquired lock to be released.


### -param _Requires_lock_held_

TBD




#### - LockState [in]

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
    <a href="..\ndis\nf-ndis-ndisacquirereadwritelock.md">NdisAcquireReadWriteLock</a> function
    to acquire a lock before the driver can call 
    <b>NdisReleaseReadWriteLock</b>. Each call to 
    <b>NdisAcquireReadWriteLock</b> requires a reciprocal call to 
    <b>NdisReleaseReadWriteLock</b>.

<b>NdisReleaseReadWriteLock</b> restores the original IRQL that was used by its caller before the call to 
    <a href="..\ndis\nf-ndis-ndisacquirereadwritelock.md">NdisAcquireReadWriteLock</a> was made.




## -see-also

<a href="..\ndis\nf-ndis-ndisreleaserwlock.md">NdisReleaseRWLock</a>



<a href="..\ndis\nf-ndis-ndisacquirereadwritelock.md">NdisAcquireReadWriteLock</a>



<a href="..\ndis\ns-ndis-_ndis_rw_lock.md">NDIS_RW_LOCK</a>



<a href="..\ndis\ns-ndis-_lock_state.md">LOCK_STATE</a>



<a href="..\ndis\ns-ndis-_ndis_rw_lock.md">NDIS_RW_LOCK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisReleaseReadWriteLock function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

