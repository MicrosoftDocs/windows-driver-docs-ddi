---
UID: NF:fltkernel.FltAcquirePushLockSharedEx
title: FltAcquirePushLockSharedEx function (fltkernel.h)
description: The FltAcquirePushLockSharedEx routine acquires the given push lock for shared access by the calling thread.
ms.date: 08/11/2022
tech.root: ifsk
keywords: ["FltAcquirePushLockSharedEx function"]
ms.keywords: FltAcquirePushLockSharedEx
req.header: fltkernel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: FltMgr.lib
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - FltAcquirePushLockSharedEx
 - fltkernel/FltAcquirePushLockSharedEx
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - FltMgr.lib
 - FltMgr.sys
api_name:
 - FltAcquirePushLockSharedEx
dev_langs:
 - c++
---

# FltAcquirePushLockSharedEx function

## -description

The **FltAcquirePushLockSharedEx** routine acquires the given push lock for shared access by the calling thread.

## -parameters

### -param PushLock

Opaque push lock pointer. This pointer must have been initialized by a previous call to [**FltInitializePushLock**](nf-fltkernel-fltinitializepushlock.md).

### -param Flags

A bitmask of flags that control the attributes of the lock.

## -returns

None.

## -remarks

The **FltAcquirePushLockSharedEx** routine acquires the given push lock for shared access by the calling thread.

Push locks are similar to ERESOURCE structures (also called resources) in that they can be acquired for shared or exclusive access. For more information about push locks, see the reference entry for [**FltInitializePushLock**](nf-fltkernel-fltinitializepushlock.md).

Unlike ERESOURCE structures, push locks cannot be acquired recursively. If the caller already has acquired the push lock for exclusive access, the system will hang. If the caller already has acquired the push lock for shared access, it can receive shared access again. However, each call to **FltAcquirePushLockShared** must be matched by a subsequent call to [**FltReleasePushLock**](nf-fltkernel-fltreleasepushlock.md).

When the caller will be given shared access to the given push lock depends on the following:

* If the push lock is currently unowned, shared access is granted immediately to the current thread.

* If the push lock has already been acquired for shared access by another thread and no thread is waiting for exclusive access to the push lock, shared access is granted to the caller immediately. The caller is put into a wait state if there is an exclusive waiter.

* If the push lock has already been acquired for exclusive access by another thread or if there is another thread waiting for exclusive access, the current thread is put into a wait state until the push lock can be acquired.

## -see-also

[**FltInitializePushLock**](nf-fltkernel-fltinitializepushlock.md)
