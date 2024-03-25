---
UID: NF:wdm.ExAcquireRundownProtectionCacheAwareEx
tech.root: kernel
title: ExAcquireRundownProtectionCacheAwareEx (wdm.h)
ms.date: 02/16/2024
targetos: Windows
description: This topic describes the ExAcquireRundownProtectionCacheAwareEx function.
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
 - ExAcquireRundownProtectionCacheAwareEx
f1_keywords:
 - ExAcquireRundownProtectionCacheAwareEx
 - wdm/ExAcquireRundownProtectionCacheAwareEx
dev_langs:
 - c++
helpviewer_keywords:
 - ExAcquireRundownProtectionCacheAwareEx
---

## -description

The **ExAcquireRundownProtectionCacheAwareEx** routine tries to acquire cache-aware run-down protection on a shared object so the caller can safely access the object.

## -parameters

### -param RunRefCacheAware [in, out]

Pointer to the opaque **EX_RUNDOWN_REF_CACHE_AWARE** structure returned by a previous call to [**ExAllocateCacheAwareRundownProtection**](./nf-wdm-exallocatecacheawarerundownprotection.md) or [**ExInitializeRundownProtectionCacheAware**](./nf-wdm-exinitializerundownprotectioncacheaware.md).

### -param Count [in]

The amount by which to increment to the run-down instance count of the object. The count is incremented only if the routine returns **TRUE**. For more information, see Remarks.

## -returns

**ExAcquireRundownProtectionCacheAwareEx** returns **TRUE** if the routine successfully acquires run-down protection for the caller. Otherwise, it returns **FALSE**. A return value of **FALSE** indicates that the run down of the object has started and that the object must be treated as invalid.

## -remarks

The *RunRefCacheAware* parameter points to an  **EX_RUNDOWN_REF_CACHE_AWARE** structure that tracks the run-down status of the associated object. This status information includes a count of instances of cache-aware run-down protection that are currently in effect on the object. The **ExAcquireRundownProtectionCacheAwareEx** and [**ExReleaseRundownProtectionCacheAwareEx**](./nf-wdm-exreleaserundownprotectioncacheawareex.md) routines increment and decrement this count by arbitrary amounts. Two related routines,  [**ExAcquireRundownProtectionCacheAware**](./nf-wdm-exacquirerundownprotectioncacheaware.md) and [**ExReleaseRundownProtectionCacheAware**](./nf-wdm-exreleaserundownprotectioncacheaware.md), increment and decrement this count by one.

As long as the run-down block itself is nonpaged, this function can be called at DISPATCH_LEVEL.

For more information, see [Cache-aware run-down protection](/windows-hardware/drivers/kernel/run-down-protection#cache-aware-run-down-protection).

## -see-also

[**ExAcquireRundownProtectionCacheAware**](./nf-wdm-exacquirerundownprotectioncacheaware.md)

[**ExAllocateCacheAwareRundownProtection**](./nf-wdm-exallocatecacheawarerundownprotection.md)

[**ExFreeCacheAwareRundownProtection**](./nf-wdm-exfreecacheawarerundownprotection.md)

[**ExInitializeRundownProtectionCacheAware**](./nf-wdm-exinitializerundownprotectioncacheaware.md)

[**ExReInitializeRundownProtectionCacheAware**](./nf-wdm-exreinitializerundownprotectioncacheaware.md)

[**ExReleaseRundownProtectionCacheAware**](./nf-wdm-exreleaserundownprotectioncacheaware.md)

[**ExReleaseRundownProtectionCacheAwareEx**](./nf-wdm-exreleaserundownprotectioncacheawareex.md)

[**ExRundownCompletedCacheAware**](./nf-wdm-exrundowncompletedcacheaware.md)

[**ExSizeOfRundownProtectionCacheAware**](./nf-wdm-exsizeofrundownprotectioncacheaware.md)

[**ExWaitForRundownProtectionReleaseCacheAware**](./nf-wdm-exwaitforrundownprotectionreleasecacheaware.md)
