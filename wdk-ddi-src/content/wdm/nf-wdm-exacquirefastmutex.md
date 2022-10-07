---
UID: NF:wdm.ExAcquireFastMutex
tech.root: kernel
title: ExAcquireFastMutex
ms.date: 10/03/2022
targetos: Windows
description: Learn more about the ExAcquireFastMutex routine.
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
 - ExAcquireFastMutex
f1_keywords:
 - ExAcquireFastMutex
 - wdm/ExAcquireFastMutex
dev_langs:
 - c++
helpviewer_keywords:
 - ExAcquireFastMutex
---

## -description

The **ExAcquireFastMutex** routine acquires the given fast mutex with APCs to the current thread disabled.

## -parameters

### -param FastMutex

[in, out] A pointer to an initialized fast mutex for which the caller provides the storage.

## -remarks

**ExAcquireFastMutex** puts the caller into a wait state if the given fast mutex cannot be acquired immediately. Otherwise, the caller is given ownership of the fast mutex with APCs to the current thread disabled until it releases the fast mutex.

Use [**ExTryToAcquireFastMutex**](nf-wdm-extrytoacquirefastmutex.md) if the current thread can do other work before it waits on the acquisition of the given mutex.

Any fast mutex that is acquired using **ExAcquireFastMutex** or **ExTryToAcquireFastMutex** must be released with [**ExReleaseFastMutex**](nf-wdm-exreleasefastmutex.md).

For more information about fast mutexes, see [Fast Mutexes and Guarded Mutexes](/windows-hardware/drivers/kernel/fast-mutexes-and-guarded-mutexes).

Callers of **ExAcquireFastMutex** must be running at IRQL \<= APC\_LEVEL. **ExAcquireFastMutex** sets the IRQL to APC\_LEVEL, and the caller continues to run at APC\_LEVEL after **ExAcquireFastMutex** returns. **ExAcquireFastMutex** saves the caller's previous IRQL in the mutex, however, and that IRQL is restored when the caller invokes **ExReleaseFastMutex**.

## -see-also

[**FAST\_MUTEX**](/windows-hardware/drivers/kernel/fast-mutexes-and-guarded-mutexes#fast-mutexes)

[**ExAcquireFastMutexUnsafe**](nf-wdm-exacquirefastmutexunsafe.md)

[**ExInitializeFastMutex**](nf-wdm-exinitializefastmutex.md)

[**ExReleaseFastMutex**](nf-wdm-exreleasefastmutex.md)

[**ExTryToAcquireFastMutex**](nf-wdm-extrytoacquirefastmutex.md)
