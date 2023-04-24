---
UID: NF:wdm.ExReleaseFastMutex
tech.root: kernel
title: ExReleaseFastMutex
ms.date: 10/03/2022
targetos: Windows
description: Learn more about the ExReleaseFastMutex routine.
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
 - ExReleaseFastMutex
f1_keywords:
 - ExReleaseFastMutex
 - wdm/ExReleaseFastMutex
dev_langs:
 - c++
helpviewer_keywords:
 - ExReleaseFastMutex
---

## -description

The **ExReleaseFastMutex** routine releases ownership of a fast mutex that was acquired with [**ExAcquireFastMutex**](nf-wdm-exacquirefastmutex.md) or [**ExTryToAcquireFastMutex**](nf-wdm-extrytoacquirefastmutex.md).

## -parameters

### -param FastMutex

[in, out] A pointer to the fast mutex to be released.

## -remarks

**ExReleaseFastMutex** releases ownership of the given fast mutex and sets the IRQL to the value that the caller was running at before it called [**ExAcquireFastMutex**](nf-wdm-exacquirefastmutex.md). If the previous IRQL was less than APC\_LEVEL, the delivery of APCs to the current thread is reenabled.

It is a programming error to call **ExReleaseFastMutex** with a *FastMutex* that was acquired using **ExAcquireFastMutexUnsafe**. Drivers should release a fast mutex from the same thread that acquired it. Fast mutexes should be released in the opposite order from the order they were acquired.

For more information about fast mutexes, see [Fast Mutexes and Guarded Mutexes](/windows-hardware/drivers/kernel/fast-mutexes-and-guarded-mutexes).

Callers of **ExReleaseFastMutex** must be running at IRQL = APC\_LEVEL. In most cases the IRQL will already be set to APC\_LEVEL before **ExReleaseFastMutex** is called because **ExAcquireFastMutex** has already set the IRQL to APC\_LEVEL automatically. However, if the caller changes the IRQL after **ExAcquireFastMutex** returns, the caller must explicitly set the IRQL to APC\_LEVEL prior to calling **ExReleaseFastMutex**.

## -see-also

[**FAST\_MUTEX**](/windows-hardware/drivers/kernel/fast-mutexes-and-guarded-mutexes#fast-mutexes)

[**ExAcquireFastMutex**](nf-wdm-exacquirefastmutex.md)

[**ExInitializeFastMutex**](nf-wdm-exinitializefastmutex.md)

[**ExTryToAcquireFastMutex**](nf-wdm-extrytoacquirefastmutex.md)
