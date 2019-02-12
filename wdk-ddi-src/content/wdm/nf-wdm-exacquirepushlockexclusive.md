---
UID: NF:wdm.ExAcquirePushLockExclusive
title: ExAcquirePushLockExclusive macro (wdm.h)
description: Acquires the given push lock for exclusive access by the calling thread.
ms.assetid: ba752619-f885-4977-b0e6-7c0339373b78
ms.date: 09/30/2018
ms.topic: macro
ms.keywords: ExAcquirePushLockExclusive
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt:  Windows 10, version 1809
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
-	HeaderDef
api_location: 
-	wdm.h
api_name: 
-	ExAcquirePushLockExclusive
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# ExAcquirePushLockExclusive macro


## -description

Acquires the given push lock for exclusive access by the calling thread.

## -parameters

### -param Lock
Opaque push lock pointer. This pointer must have been initialized by a previous call to [**ExInitializePushLock**](nf-wdm-exinitializepushlock.md).

## -remarks

Push locks are similar to ERESOURCE structures (also called resources) in that they can be acquired for shared or exclusive access. For more information about push locks, see the reference entry for [**ExInitializePushLock**](nf-wdm-exinitializepushlock.md).

Unlike ERESOURCE structures, push locks cannot be acquired recursively. If the caller already has acquired the push lock for exclusive or shared access, the thread hangs. 
When the caller is given exclusive access to the given push lock, depends on the following:

- If the push lock is currently unowned, exclusive access is granted immediately to the current thread.

- If the push lock has already been acquired for exclusive or shared access by another thread, the current thread is put into a wait state until the push lock can be acquired. 

The caller is required call  [**KeEnterCriticalRegion**](..//ntddk/nf-ntddk-keentercriticalregion) before calling **ExAcquirePushLockExclusive**.

To release the push lock after it is acquired, call [**ExReleasePushLockExclusive**](nf-wdm-exreleasepushlockexclusive.md). Every call to ExAcquirePushLockExclusive must be matched by a subsequent call to [**ExReleasePushLockExclusive**](nf-wdm-exreleasepushlockexclusive.md).

To acquire a push lock for shared access, call [**ExAcquirePushLockShared**](nf-wdm-exacquirepushlockshared.md).



## -see-also
[**ExInitializePushLock**](nf-wdm-exinitializepushlock.md)

[**KeEnterCriticalRegion**](..//ntddk/nf-ntddk-keentercriticalregion)

[**ExReleasePushLockExclusive**](nf-wdm-exreleasepushlockexclusive.md)

[**ExAcquirePushLockShared**](nf-wdm-exacquirepushlockshared.md)

