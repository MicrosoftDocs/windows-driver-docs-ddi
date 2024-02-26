---
UID: NF:wdm.ExAllocateCacheAwareRundownProtection
tech.root: kernel
title: ExAllocateCacheAwareRundownProtection (wdm.h)
ms.date: 02/13/2023
targetos: Windows
description: This topic describes the ExAllocateCacheAwareRundownProtection function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql: <= APC_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr:  Windows Server 2003, Service Pack 1
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - wdm.h
api_name:
 - ExAllocateCacheAwareRundownProtection
f1_keywords:
 - ExAllocateCacheAwareRundownProtection
 - wdm/ExAllocateCacheAwareRundownProtection
dev_langs:
 - c++
helpviewer_keywords:
 - ExAllocateCacheAwareRundownProtection
---

## -description

The **ExAllocateCacheAwareRundownProtection** routine allocates a cache-friendly rundown protection structure for multi-processor scenarios. Rundown protection is a synchronization mechanism that allows for the safe cleanup of resources that might be accessed by multiple threads.

## -parameters

### -param PoolType [in]

The type of pool memory to allocate. For a description of the available pool memory types, see [**POOL_TYPE**](ne-wdm-_pool_type.md).

### -param PoolTag [in]

A ULONG that specifies the pool tag for the memory allocation. The pool tag is a 32-bit value that is used to track memory usage.

## -returns

Returns a pointer to an opaque **EX_RUNDOWN_REF_CACHE_AWARE** structure or NULL if allocation fails.

## -remarks

A driver can call **ExAllocateCacheAwareRundownProtection** as an alternative to calling [**ExSizeOfRundownProtectionCacheAware**](/windows-hardware/drivers/ddi/wdm/nf-wdm-exsizeofrundownprotectioncacheaware) followed by [**ExInitializeRundownProtectionCacheAware**](/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializerundownprotectioncacheaware).

For more info, see [Cache-aware run-down protection](/windows-hardware/drivers/kernel/run-down-protection#cache-aware-run-down-protection).

## -see-also

[**ExAcquireRundownProtectionCacheAware**](./nf-wdm-exacquirerundownprotectioncacheaware.md)

[**ExAcquireRundownProtectionCacheAwareEx**](./nf-wdm-exacquirerundownprotectioncacheawareex.md)

[**ExFreeCacheAwareRundownProtection**](./nf-wdm-exfreecacheawarerundownprotection.md)

[**ExInitializeRundownProtectionCacheAware**](./nf-wdm-exinitializerundownprotectioncacheaware.md)

[**ExReInitializeRundownProtectionCacheAware**](./nf-wdm-exreinitializerundownprotectioncacheaware.md)

[**ExReleaseRundownProtectionCacheAware**](./nf-wdm-exreleaserundownprotectioncacheaware.md)

[**ExReleaseRundownProtectionCacheAwareEx**](./nf-wdm-exreleaserundownprotectioncacheawareex.md)

[**ExRundownCompletedCacheAware**](./nf-wdm-exrundowncompletedcacheaware.md)

[**ExSizeOfRundownProtectionCacheAware**](./nf-wdm-exsizeofrundownprotectioncacheaware.md)

[**ExWaitForRundownProtectionReleaseCacheAware**](./nf-wdm-exwaitforrundownprotectionreleasecacheaware.md)
