---
UID: NF:wdm.KeAcquireGuardedMutex
tech.root: kernel
title: KeAcquireGuardedMutex
ms.date: 10/05/2022
targetos: Windows
description: Learn more about the KeAcquireGuardedMutex routine.
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
 - KeAcquireGuardedMutex
f1_keywords:
 - KeAcquireGuardedMutex
 - wdm/KeAcquireGuardedMutex
dev_langs:
 - c++
helpviewer_keywords:
 - KeAcquireGuardedMutex
---

## -description

The **KeAcquireGuardedMutex** routine acquires a guarded mutex.

## -parameters

### -param Mutex

[in, out] Pointer to the [**KGUARDED\_MUTEX**](/windows-hardware/drivers/kernel/eprocess) structure for the guarded mutex. This structure must have been initialized with [**KeInitializeGuardedMutex**](nf-wdm-keinitializeguardedmutex.md).

## -remarks

Use [**KeReleaseGuardedMutex**](nf-wdm-kereleaseguardedmutex.md) to release a mutex acquired with **KeAcquireGuardedMutex**.

If the mutex is available, **KeAcquireGuardedMutex** returns immediately. Otherwise, the calling thread is put in a wait state until the mutex becomes available. To avoid entering a wait state when the mutex is unavailable, use [**KeTryToAcquireGuardedMutex**](nf-wdm-ketrytoacquireguardedmutex.md).

A thread that calls **KeAcquireGuardedMutex** implicitly enters a guarded region, where all APCs are disabled. They remain disabled until the thread releases the mutex with **KeReleaseGuardedMutex**.

A guarded mutex cannot be acquired recursively: if a thread is already holding the mutex when it calls **KeAcquireGuardedMutex**, the thread will deadlock.

For more information about guarded mutexes, see [Fast Mutexes and Guarded Mutexes](/windows-hardware/drivers/kernel/fast-mutexes-and-guarded-mutexes).

## -see-also

[**KGUARDED\_MUTEX**](/windows-hardware/drivers/kernel/eprocess)

[**KeReleaseGuardedMutex**](nf-wdm-kereleaseguardedmutex.md)
