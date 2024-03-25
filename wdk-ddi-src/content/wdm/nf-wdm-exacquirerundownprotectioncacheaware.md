---
UID: NF:wdm.ExAcquireRundownProtectionCacheAware
tech.root: kernel
title: ExAcquireRundownProtectionCacheAware (wdm.h)
ms.date: 02/16/2024
targetos: Windows
description: This topic describes the ExAcquireRundownProtectionCacheAware function.
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
 - ExAcquireRundownProtectionCacheAware
f1_keywords:
 - ExAcquireRundownProtectionCacheAware
 - wdm/ExAcquireRundownProtectionCacheAware
dev_langs:
 - c++
helpviewer_keywords:
 - ExAcquireRundownProtectionCacheAware
---

## -description

The **ExAcquireRundownProtectionCacheAware** routine tries to acquire cache-aware run-down protection on a shared object so the caller can safely access the object.

## -parameters

### -param RunRefCacheAware [in, out]

Pointer to the opaque **EX_RUNDOWN_REF_CACHE_AWARE** structure returned by a previous call to [**ExAllocateCacheAwareRundownProtection**](./nf-wdm-exallocatecacheawarerundownprotection.md) or [**ExInitializeRundownProtectionCacheAware**](./nf-wdm-exinitializerundownprotectioncacheaware.md).

## -returns

Returns TRUE if rundown protection was acquired and FALSE if rundown is currently active or completed.

## -remarks

## -see-also

[Cache-aware run-down protection](/windows-hardware/drivers/kernel/run-down-protection#cache-aware-run-down-protection)

[**ExAcquireRundownProtectionCacheAwareEx**](./nf-wdm-exacquirerundownprotectioncacheawareex.md)

[**ExAllocateCacheAwareRundownProtection**](./nf-wdm-exallocatecacheawarerundownprotection.md)

[**ExFreeCacheAwareRundownProtection**](./nf-wdm-exfreecacheawarerundownprotection.md)

[**ExInitializeRundownProtectionCacheAware**](./nf-wdm-exinitializerundownprotectioncacheaware.md)

[**ExReInitializeRundownProtectionCacheAware**](./nf-wdm-exreinitializerundownprotectioncacheaware.md)

[**ExReleaseRundownProtectionCacheAware**](./nf-wdm-exreleaserundownprotectioncacheaware.md)

[**ExReleaseRundownProtectionCacheAwareEx**](./nf-wdm-exreleaserundownprotectioncacheawareex.md)

[**ExRundownCompletedCacheAware**](./nf-wdm-exrundowncompletedcacheaware.md)

[**ExSizeOfRundownProtectionCacheAware**](./nf-wdm-exsizeofrundownprotectioncacheaware.md)

[**ExWaitForRundownProtectionReleaseCacheAware**](./nf-wdm-exwaitforrundownprotectionreleasecacheaware.md)
