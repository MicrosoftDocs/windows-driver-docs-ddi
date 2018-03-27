---
UID: NF:ndis.NdisReleaseRWLock
title: NdisReleaseRWLock function
author: windows-driver-content
description: The NdisReleaseRWLock function releases a read/write lock that the caller uses to gain access to resources that are shared between driver threads.
old-location: netvista\ndisreleaserwlock.htm
old-project: netvista
ms.assetid: e0859f3f-0acc-45b7-99b2-ef420cd06565
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisReleaseRWLock, NdisReleaseRWLock function [Network Drivers Starting with Windows Vista], ndis/NdisReleaseRWLock, ndis_processor_group_ref_bbc47204-3cf6-4154-bafc-23c14cff452b.xml, netvista.ndisreleaserwlock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisReleaseRWLock
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisReleaseRWLock function


## -description


The 
  <b>NdisReleaseRWLock</b> function releases a read/write lock that the caller uses to gain access to
  resources that are shared between driver threads.


## -parameters




### -param Lock [in]

A pointer to an opaque 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> variable that represents a
     lock. The caller can use this lock to gain write or read access to resources that are shared between
     non-ISR driver threads.


### -param LockState [in]

A pointer to an opaque 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff557070">LOCK_STATE_EX</a> variable that tracks the state
     of the lock. This variable exists in the interval between the times that the caller obtains and releases
     the lock. The caller must use a different variable of type LOCK_STATE_EX for each attempt that it makes
     to obtain the lock from the same non-ISR driver thread.


## -returns



None




## -remarks



NDIS drivers call the 
    <b>NdisReleaseRWLock</b> function to release a read/write lock that was previously obtained by calling the
    
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff560697">NdisAcquireRWLockRead</a> or 
    <a href="https://msdn.microsoft.com/124302d7-0776-4025-b71f-ce6300f97f49">
    NdisAcquireRWLockWrite</a> function.

A driver must obtain a read/write lock before the driver can call 
    <b>NdisReleaseRWLock</b>. Each call to obtain a lock requires a reciprocal call to 
    <b>NdisReleaseRWLock</b>.

The acquisition of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> is affinitized to the current processor.  Drivers must call <b>NdisReleaseRWLock</b> on the same processor that made the corresponding call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff560697">NdisAcquireRWLockRead</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff560698">NdisAcquireRWLockWrite</a>.

<b>NdisReleaseRWLock</b> restores the original IRQL that was used by its caller before the lock was
    obtained.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557070">LOCK_STATE_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560697">NdisAcquireRWLockRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560698">NdisAcquireRWLockWrite</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisReleaseRWLock function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

