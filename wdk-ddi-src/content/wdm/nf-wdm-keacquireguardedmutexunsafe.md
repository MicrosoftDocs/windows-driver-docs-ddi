---
UID: NF:wdm.KeAcquireGuardedMutexUnsafe
tech.root: kernel
title: KeAcquireGuardedMutexUnsafe
ms.date: 10/05/2022
targetos: Windows
description: Learn more about the KeAcquireGuardedMutexUnsafe function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: <= APC_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2003
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DLLExport
api_location:
 - wdm.h
api_name:
 - KeAcquireGuardedMutexUnsafe
f1_keywords:
 - KeAcquireGuardedMutexUnsafe
 - wdm/KeAcquireGuardedMutexUnsafe
dev_langs:
 - c++
helpviewer_keywords:
 - KeAcquireGuardedMutexUnsafe
---

## -description

The **KeAcquireGuardedMutexUnsafe** acquires a guarded mutex while inside a guarded region.

## -parameters

### -param FastMutex

[in, out] Pointer to the [**KGUARDED\_MUTEX**](/windows-hardware/drivers/kernel/eprocess) structure for the guarded mutex.

## -remarks

Use **KeReleaseGuardedMutexUnsafe** to release a guarded mutex acquired with **KeAcquireMutexUnsafe**.

**KeAcquireGuardedMutexUnsafe** does not implicitly place the calling thread within a guarded region. Code enclosed within a **KeAcquireGuardedMutexUnsafe**/**KeReleaseGuardedMutexUnsafe** pair must execute either at IRQL = APC\_LEVEL, or within a guarded region. For code that is not guaranteed to execute within a guarded region, use **KeAcquireGuardedMutex** and **KeReleaseGuardedMutexUnsafe**.

A guarded mutex cannot be acquired recursively: if a thread is already holding the mutex when it calls **KeAcquireGuardedMutexUnsafe**, the thread will deadlock.

For more information about guarded mutexes, see [Fast Mutexes and Guarded Mutexes](/windows-hardware/drivers/kernel/fast-mutexes-and-guarded-mutexes).

## -see-also

[**KGUARDED\_MUTEX**](/windows-hardware/drivers/kernel/eprocess)

[**KeReleaseGuardedMutexUnsafe**](nf-wdm-kereleaseguardedmutexunsafe.md)
