---
UID: NF:wdm.ExTryAcquirePushLockExclusive
tech.root: kernel
title: ExTryAcquirePushLockExclusive
ms.date: 03/19/2025
targetos: Windows
description: Try to acquire the given push lock for exclusive access by the calling thread.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
returns-override: true
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - ExTryAcquirePushLockExclusive
f1_keywords:
 - ExTryAcquirePushLockExclusive
 - wdm/ExTryAcquirePushLockExclusive
dev_langs:
 - c++
helpviewer_keywords:
 - ExTryAcquirePushLockExclusive
---

## -description

Try to acquire the given push lock for exclusive access by the calling thread.

## -parameters

### -param Lock

Opaque push lock pointer. This pointer must have been initialized by a previous call to [**ExInitializePushLock**](nf-wdm-exinitializepushlock.md).

## -returns

If the lock is successfully acquired, the return value is nonzero. If the current thread could not acquire the lock, the return value is zero.

## -remarks

Push locks are similar to ERESOURCE structures (also called resources) in that they can be acquired for shared or exclusive access. For more information about push locks, see the reference entry for [**ExInitializePushLock**](nf-wdm-exinitializepushlock.md).

Unlike ERESOURCE structures, push locks cannot be acquired recursively. If the caller already has acquired the push lock for exclusive or shared access, the thread hangs. 
When the caller is given exclusive access to the given push lock, depends on the following:

- If the push lock is currently unowned, exclusive access is granted immediately to the current thread.

- If the push lock has already been acquired for exclusive or shared access by another thread, the current thread is put into a wait state until the push lock can be acquired.

Before calling this routine, the driver must disable normal kernel APC delivery by calling [**KeEnterCriticalRegion**](../ntddk/nf-ntddk-keentercriticalregion.md). Reenable delivery after the push lock is released by calling [**KeLeaveCriticalRegion**](../ntddk/nf-ntddk-keleavecriticalregion.md). For more information, see [Disabling APCs](/windows-hardware/drivers/kernel/disabling-apcs).

To release the push lock after it is acquired, call [**ExReleasePushLockExclusive**](nf-wdm-exreleasepushlockexclusive.md). Every call to ExAcquirePushLockExclusive must be matched by a subsequent call to [**ExReleasePushLockExclusive**](nf-wdm-exreleasepushlockexclusive.md).

To acquire a push lock for shared access, call [**ExAcquirePushLockShared**](nf-wdm-exacquirepushlockshared.md).

## -see-also

[ExTryAcquirePushLockShared](nf-wdm-extryacquirepushlockshared.md)

[ExInitializePushLock](nf-wdm-exinitializepushlock.md)

[KeEnterCriticalRegion](../ntddk/nf-ntddk-keentercriticalregion.md)

[ExReleasePushLockExclusive](nf-wdm-exreleasepushlockexclusive.md)

[ExAcquirePushLockShared](nf-wdm-exacquirepushlockshared.md)

## -syntax

```cpp
BOOLEAN ExTryAcquirePushLockExclusive(
   Lock
);
```
