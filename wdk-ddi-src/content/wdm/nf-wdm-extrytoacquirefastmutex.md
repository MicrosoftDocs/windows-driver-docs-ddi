---
UID: NF:wdm.ExTryToAcquireFastMutex
tech.root: kernel
title: ExTryToAcquireFastMutex
ms.date: 10/05/2022
targetos: Windows
description: Learn more about the ExTryToAcquireFastMutex routine.
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
 - ExTryToAcquireFastMutex
f1_keywords:
 - ExTryToAcquireFastMutex
 - wdm/ExTryToAcquireFastMutex
dev_langs:
 - c++
helpviewer_keywords:
 - ExTryToAcquireFastMutex
---

## -description

The **ExTryToAcquireFastMutex** routine acquires the given fast mutex, if possible, with APCs to the current thread disabled.

## -parameters

### -param FastMutex

[in, out] A pointer to the fast mutex to be acquired if it is not currently owned by another thread.

## -returns

**ExTryToAcquireFastMutex** returns **TRUE** if the current thread is given ownership of the fast mutex.

## -remarks

If the given fast mutex is currently unowned, **ExTryToAcquireFastMutex** gives the caller ownership with APCs to the current thread disabled until it releases the fast mutex.

Use [**ExAcquireFastMutex**](nf-wdm-exacquirefastmutex.md) if the current thread must wait for the acquisition of the given mutex before it can do useful work.

Any fast mutex that is acquired with **ExTryToAcquireFastMutex** or [**ExAcquireFastMutex**](nf-wdm-exacquirefastmutex.md) must be released with [**ExReleaseFastMutex**](nf-wdm-exreleasefastmutex.md).

For more information about fast mutexes, see [Fast Mutexes and Guarded Mutexes](/windows-hardware/drivers/kernel/fast-mutexes-and-guarded-mutexes).

Callers of **ExTryToAcquireFastMutex** must be running at IRQL \<= APC\_LEVEL. **ExTryToAcquireFastMutex** sets the IRQL to APC\_LEVEL if the mutex is acquired, and the caller continues to run at APC\_LEVEL after **ExTryToAcquireFastMutex** returns. **ExTryToAcquireFastMutex** saves the caller's previous IRQL in the mutex if successful, however, and that IRQL is restored when the caller calls **ExReleaseFastMutex**.

## -see-also

[**FAST\_MUTEX**](/windows-hardware/drivers/kernel/fast-mutexes-and-guarded-mutexes#fast-mutexes)

[**ExAcquireFastMutex**](nf-wdm-exacquirefastmutex.md)

[**ExInitializeFastMutex**](nf-wdm-exinitializefastmutex.md)

[**ExReleaseFastMutex**](nf-wdm-exreleasefastmutex.md)
