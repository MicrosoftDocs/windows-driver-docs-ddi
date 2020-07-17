---
UID: NF:wdm.ExAcquirePushLockShared
title: ExAcquirePushLockShared macro (wdm.h)
description: Acquires the given push lock for shared access by the calling thread.
ms.assetid: de40a669-9154-4ad6-bed3-75e66ee2b864
ms.date: 09/30/2018
keywords: ["ExAcquirePushLockShared macro"]
f1_keywords:
 - "wdm/ExAcquirePushLockShared"
 - "ExAcquirePushLockShared"
ms.keywords: ExAcquirePushLockShared
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
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
- apiref
api_type: 
- HeaderDef
api_location: 
- wdm.h
api_name: 
- ExAcquirePushLockShared
product:
- Windows
targetos: Windows

ms.custom: RS5
---

# ExAcquirePushLockShared macro


## -description

Acquires the given push lock for shared access by the calling thread.

## -parameters

### -param Lock
Opaque push lock pointer. This pointer must have been initialized by a previous call to [**ExInitializePushLock**](nf-wdm-exinitializepushlock.md).

## -remarks
Push locks are similar to ERESOURCE structures (also called resources) in that they can be acquired for shared or exclusive access. For more information about push locks, see the reference entry for [**ExInitializePushLock**](nf-wdm-exinitializepushlock.md).

Unlike ERESOURCE structures, push locks cannot be acquired recursively. If the caller already has acquired the push lock for exclusive access, the system will hang. If the caller already has acquired the push lock for shared access, it can receive shared access again. 

To release the push lock after it is acquired, call [**ExReleasePushLockShared**](nf-wdm-exreleasepushlockshared.md). Each call to **ExAcquirePushLockShared** must be matched by a subsequent call to [**ExReleasePushLockShared**](nf-wdm-exreleasepushlockshared.md). 

When the caller will be given shared access to the given push lock depends on the following:

- If the push lock is currently unowned, shared access is granted immediately to the current thread.

- If the push lock has already been acquired for shared access by another thread and no thread is waiting for exclusive access to the push lock, shared access is granted to the caller immediately. The caller is put into a wait state if there is an exclusive waiter.

- If the push lock has already been acquired for exclusive access by another thread or if there is another thread waiting for exclusive access, the current thread is put into a wait state until the push lock can be acquired.

The caller is required call  [**KeEnterCriticalRegion**](../ntddk/nf-ntddk-keentercriticalregion.md) before calling **ExAcquirePushLockShared**.

To acquire a push lock for exclusive access, call [**ExAcquirePushLockExclusive**](nf-wdm-exacquirepushlockexclusive.md). 


## -see-also

[**ExInitializePushLock**](nf-wdm-exinitializepushlock.md)

[**KeEnterCriticalRegion**](../ntddk/nf-ntddk-keentercriticalregion.md)

[**ExReleasePushLockShared**](nf-wdm-exreleasepushlockshared.md)

[**ExAcquirePushLockExclusive**](nf-wdm-exacquirepushlockexclusive.md)
