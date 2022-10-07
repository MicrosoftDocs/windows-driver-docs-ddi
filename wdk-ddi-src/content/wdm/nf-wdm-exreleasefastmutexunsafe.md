---
UID: NF:wdm.ExReleaseFastMutexUnsafe
tech.root: kernel
title: ExReleaseFastMutexUnsafe
ms.date: 10/05/2022
targetos: Windows
description: Learn more about the ExReleaseFastMutexUnsafe routine.
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
 - ExReleaseFastMutexUnsafe
f1_keywords:
 - ExReleaseFastMutexUnsafe
 - wdm/ExReleaseFastMutexUnsafe
dev_langs:
 - c++
helpviewer_keywords:
 - ExReleaseFastMutexUnsafe
---

## -description

The **ExReleaseFastMutexUnsafe** routine releases ownership of a fast mutex that was acquired by using [**ExAcquireFastMutexUnsafe**](nf-wdm-exacquirefastmutexunsafe.md).

## -parameters

### -param FastMutex

[in, out] A pointer to the fast mutex to be released.

## -remarks

It is a programming error to call **ExReleaseFastMutexUnsafe** with a pointer to a fast mutex that was acquired by using [**ExAcquireFastMutex**](nf-wdm-exacquirefastmutex.md) or [**ExTryToAcquireFastMutex**](nf-wdm-extrytoacquirefastmutex.md).

For more information about fast mutexes, see [Fast Mutexes and Guarded Mutexes](/windows-hardware/drivers/kernel/fast-mutexes-and-guarded-mutexes).

## -see-also

[**FAST\_MUTEX**](/windows-hardware/drivers/kernel/fast-mutexes-and-guarded-mutexes#fast-mutexes)

[**ExAcquireFastMutex**](nf-wdm-exacquirefastmutex.md)

[**ExAcquireFastMutexUnsafe**](nf-wdm-exacquirefastmutexunsafe.md)

[**ExInitializeFastMutex**](nf-wdm-exinitializefastmutex.md)

[**ExTryToAcquireFastMutex**](nf-wdm-extrytoacquirefastmutex.md)
