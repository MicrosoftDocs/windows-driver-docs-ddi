---
UID: NF:wdm.ExFreeCacheAwareRundownProtection
tech.root: kernel
title: ExFreeCacheAwareRundownProtection (wdm.h)
ms.date: 02/23/2024
targetos: Windows
description: This topic describes the ExFreeCacheAwareRundownProtection function.
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
 - ExFreeCacheAwareRundownProtection
f1_keywords:
 - ExFreeCacheAwareRundownProtection
 - wdm/ExFreeCacheAwareRundownProtection
dev_langs:
 - c++
helpviewer_keywords:
 - ExFreeCacheAwareRundownProtection
---

## -description

The **ExFreeCacheAwareRundownProtection** routine frees a cache-friendly rundown protection structure that was previously allocated.

## -parameters

### -param RunRefCacheAware [in, out]

Pointer to the rundown protection object to be freed. This is a pointer to an opaque **EX_RUNDOWN_REF_CACHE_AWARE** structure returned from a previous call to [**ExAllocateCacheAwareRundownProtection**](./nf-wdm-exallocatecacheawarerundownprotection.md) or [**ExAllocateCacheAwareRundownProtection**](./nf-wdm-exallocatecacheawarerundownprotection.md).

## -remarks

For more info, see [Cache-aware run-down protection](/windows-hardware/drivers/kernel/run-down-protection#cache-aware-run-down-protection).

## -see-also

[**ExAcquireRundownProtectionCacheAware**](./nf-wdm-exacquirerundownprotectioncacheaware.md)

[**ExAcquireRundownProtectionCacheAwareEx**](./nf-wdm-exacquirerundownprotectioncacheawareex.md)

[**ExAllocateCacheAwareRundownProtection**](./nf-wdm-exallocatecacheawarerundownprotection.md)

[**ExInitializeRundownProtectionCacheAware**](./nf-wdm-exinitializerundownprotectioncacheaware.md)

[**ExReInitializeRundownProtectionCacheAware**](./nf-wdm-exreinitializerundownprotectioncacheaware.md)

[**ExReleaseRundownProtectionCacheAware**](./nf-wdm-exreleaserundownprotectioncacheaware.md)

[**ExReleaseRundownProtectionCacheAwareEx**](./nf-wdm-exreleaserundownprotectioncacheawareex.md)

[**ExRundownCompletedCacheAware**](./nf-wdm-exrundowncompletedcacheaware.md)

[**ExSizeOfRundownProtectionCacheAware**](./nf-wdm-exsizeofrundownprotectioncacheaware.md)

[**ExWaitForRundownProtectionReleaseCacheAware**](./nf-wdm-exwaitforrundownprotectionreleasecacheaware.md)
