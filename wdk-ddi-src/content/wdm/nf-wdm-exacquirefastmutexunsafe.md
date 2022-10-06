---
UID: NF:wdm.ExAcquireFastMutexUnsafe
tech.root: kernel
title: ExAcquireFastMutexUnsafe
ms.date: 10/03/2022
targetos: Windows
description: Learn more about the ExAcquireFastMutexUnsafe routine.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: APC_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 2000
req.target-min-winversvr: 
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
 - ExAcquireFastMutexUnsafe
f1_keywords:
 - ExAcquireFastMutexUnsafe
 - wdm/ExAcquireFastMutexUnsafe
dev_langs:
 - c++
helpviewer_keywords:
 - ExAcquireFastMutexUnsafe
---

## -description

The **ExAcquireFastMutexUnsafe** routine acquires the specified fast mutex for the calling thread.

## -parameters

### -param FastMutex

[in, out] A pointer to a [**FAST\_MUTEX**](/windows-hardware/drivers/kernel/fast-mutexes-and-guarded-mutexes#fast-mutexes)) structure that the caller provides the storage for. The caller previously initialized this structure by a call to the [**ExInitializeFastMutex**](nf-wdm-exinitializefastmutex.md) routine

## -remarks

**ExAcquireFastMutexUnsafe** puts the caller into a wait state if the specified fast mutex cannot be acquired immediately. Otherwise, the caller is given ownership of the mutex and exclusive access to the resource that the mutex protects until the caller releases the mutex.

Any fast mutex that is acquired by a call to **ExAcquireFastMutexUnsafe** must be released by a call to the [**ExReleaseFastMutexUnsafe**](nf-wdm-exreleasefastmutexunsafe.md) routine.

The [**ExAcquireFastMutex**](nf-wdm-exacquirefastmutex.md) and **ExAcquireFastMutexUnsafe** routines cause the calling thread to block until the mutex is available. The [**ExTryToAcquireFastMutex**](nf-wdm-extrytoacquirefastmutex.md) routine returns immediately with return value **FALSE** if another thread has already acquired the mutex. Both **ExAcquireFastMutex** and **ExTryToAcquireFastMutex** raise the IRQL to APC\_LEVEL before acquiring the fast mutex. Drivers should use **ExAcquireFastMutexUnsafe**, which does not raise the IRQL, only if either of the following is true:

  - The thread is already running at APC\_LEVEL.

  - The thread acquires the mutex within a critical region that was previously entered by a call to the [**KeEnterCriticalRegion**](nf-wdm-keentercriticalregion.md) or [**FsRtlEnterFileSystem**](/windows-hardware/drivers/ifs/fsrtlenterfilesystem) routine.

For more information about fast mutexes, see the following topics:

[Fast Mutexes and Guarded Mutexes](/windows-hardware/drivers/kernel/fast-mutexes-and-guarded-mutexes)

[Locks, Deadlocks, and Synchronization](/windows-hardware/drivers/kernel/introduction-to-spin-locks)

## -see-also

[**ExAcquireFastMutex**](nf-wdm-exacquirefastmutex.md)

[**ExInitializeFastMutex**](nf-wdm-exinitializefastmutex.md)

[**ExReleaseFastMutexUnsafe**](nf-wdm-exreleasefastmutexunsafe.md)

[**ExTryToAcquireFastMutex**](nf-wdm-extrytoacquirefastmutex.md)

[**FAST\_MUTEX**](/windows-hardware/drivers/kernel/fast-mutexes-and-guarded-mutexes#fast-mutexes)

[**FsRtlEnterFileSystem**](/windows-hardware/drivers/ifs/fsrtlenterfilesystem)

[**KeEnterCriticalRegion**](nf-wdm-keentercriticalregion.md)

[**KeLeaveCriticalRegion**](nf-wdm-keleavecriticalregion.md)
