---
UID: NF:wdm.ExWaitForRundownProtectionReleaseCacheAware
tech.root: kernel
title: ExWaitForRundownProtectionReleaseCacheAware (wdm.h)
ms.date: 02/16/2024
targetos: Windows
description: This topic describes the ExWaitForRundownProtectionReleaseCacheAware function.
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
 - ExWaitForRundownProtectionReleaseCacheAware
f1_keywords:
 - ExWaitForRundownProtectionReleaseCacheAware
 - wdm/ExWaitForRundownProtectionReleaseCacheAware
dev_langs:
 - c++
helpviewer_keywords:
 - ExWaitForRundownProtectionReleaseCacheAware
---

## -description

The **ExWaitForRundownProtectionReleaseCacheAware** routine waits until all drivers that have already been granted cache-aware run-down protection complete their accesses of the shared object.

## -parameters

### -param RunRef [in, out]

A pointer to a **EX_RUNDOWN_REF_CACHE_AWARE** structure that was initialized by a previous call to [**ExAllocateCacheAwareRundownProtection**](./nf-wdm-exallocatecacheawarerundownprotection.md) or [**ExInitializeRundownProtectionCacheAware**](./nf-wdm-exinitializerundownprotectioncacheaware.md). The cache-aware run-down protection routines use this structure to track the run-down status of the associated shared object. This structure is opaque to drivers.

## -remarks

This routine is called by the driver that owns an object that resides in shared memory and that is accessed by other drivers. Before deleting this object, the owning driver must call this routine to wait for any outstanding accesses of the object to complete. After **ExWaitForRundownProtectionReleaseCacheAware** returns, the owning driver can safely delete the object.

After **ExWaitForRundownProtectionReleaseCacheAware** is called, the [**ExAcquireRundownProtectionCacheAware**](./nf-wdm-exacquirerundownprotectioncacheaware.md) routine grants no further requests for cache-aware run-down protection from drivers that are trying to access the shared object.

The routine waits to return until all drivers that were previously granted cache-aware run-down protection finish accessing the object. As each driver finishes, it calls the [**ExReleaseRundownProtectionCacheAware**](./nf-wdm-exreleaserundownprotectioncacheaware.md) routine to release the previously acquired cache-aware run-down protection. When all outstanding accesses are completed, **ExWaitForRundownProtectionReleaseCacheAware** returns and the object can be safely deleted.

If **ExWaitForRundownProtectionReleaseCacheAware** is called when all drivers that were previously granted run-down protection have already finished accessing the shared object, the routine changes the object status to *run down*, and returns immediately, without waiting.

If **ExWaitForRundownProtectionReleaseCacheAware** is called to run down a shared object, but the *RunRef* parameter indicates that this object is already run down, the call has no effect but is not treated as an error.

For more information, see [Cache-aware run-down protection](/windows-hardware/drivers/kernel/run-down-protection#cache-aware-run-down-protection).

## -see-also

[**ExAcquireRundownProtectionCacheAware**](./nf-wdm-exacquirerundownprotectioncacheaware.md)

[**ExAcquireRundownProtectionCacheAwareEx**](./nf-wdm-exacquirerundownprotectioncacheawareex.md)

[**ExAllocateCacheAwareRundownProtection**](./nf-wdm-exallocatecacheawarerundownprotection.md)

[**ExFreeCacheAwareRundownProtection**](./nf-wdm-exfreecacheawarerundownprotection.md)

[**ExInitializeRundownProtectionCacheAware**](./nf-wdm-exinitializerundownprotectioncacheaware.md)

[**ExReInitializeRundownProtectionCacheAware**](./nf-wdm-exreinitializerundownprotectioncacheaware.md)

[**ExReleaseRundownProtectionCacheAware**](./nf-wdm-exreleaserundownprotectioncacheaware.md)

[**ExReleaseRundownProtectionCacheAwareEx**](./nf-wdm-exreleaserundownprotectioncacheawareex.md)

[**ExRundownCompletedCacheAware**](./nf-wdm-exrundowncompletedcacheaware.md)

[**ExSizeOfRundownProtectionCacheAware**](./nf-wdm-exsizeofrundownprotectioncacheaware.md)
