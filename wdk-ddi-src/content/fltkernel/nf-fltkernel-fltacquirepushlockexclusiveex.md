---
UID: NF:fltkernel.FltAcquirePushLockExclusiveEx
title: FltAcquirePushLockExclusiveEx function
author: windows-driver-content
description: The FltAcquirePushLockExclusiveEx routine acquires the given push lock for exclusive access by the calling thread.
ms.assetid: 522e77d0-1de3-472c-abb1-5f147f247d6e
ms.author: windowsdriverdev
ms.date: 
ms.topic: function
ms.keywords: FltAcquirePushLockExclusiveEx
req.header: fltkernel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	DllExport
api_location: 
-	NtosKrnl.exe
api_name: 
-	FltAcquirePushLockExclusiveEx
product: Windows
targetos: Windows

---

# FltAcquirePushLockExclusiveEx function

## -description

The **FltAcquirePushLockExclusiveEx** routine acquires the given push lock for exclusive access by the calling thread.

## -parameters

### -param 

### -param PushLock [in, out]

Opaque push lock pointer. This pointer must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543297">FltInitializePushLock</a>. 


### -param Flags

A bitmask of flags that control the attributes of the lock.

## -remarks

<b>FltAcquirePushLockExclusiveEx</b> acquires the given push lock for exclusive access by the calling thread. 

Push locks are similar to ERESOURCE structures (also called resources) in that they can be acquired for shared or exclusive access. For more information about push locks, see the reference entry for <a href="https://msdn.microsoft.com/library/windows/hardware/ff543297">FltInitializePushLock</a>. 

Unlike ERESOURCE structures, push locks cannot be acquired recursively. If the caller already has acquired the push lock for exclusive or shared access, the thread will hang. 

When the caller will be given exclusive access to the given push lock depends on the following:

<ul>
<li>
If the push lock is currently unowned, exclusive access is granted immediately to the current thread.

</li>
<li>
If the push lock has already been acquired for exclusive or shared access by another thread, the current thread is put into a wait state until the push lock can be acquired. 

</li>
</ul>

## -see-also