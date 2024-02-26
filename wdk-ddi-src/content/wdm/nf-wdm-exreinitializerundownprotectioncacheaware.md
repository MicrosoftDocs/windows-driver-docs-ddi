---
UID: NF:wdm.ExReInitializeRundownProtectionCacheAware
tech.root: kernel
title: ExReInitializeRundownProtectionCacheAware (wdm.h)
ms.date: 02/16/2024
targetos: Windows
description: This topic describes the ExReInitializeRundownProtectionCacheAware function.
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
 - ExReInitializeRundownProtectionCacheAware
f1_keywords:
 - ExReInitializeRundownProtectionCacheAware
 - wdm/ExReInitializeRundownProtectionCacheAware
dev_langs:
 - c++
helpviewer_keywords:
 - ExReInitializeRundownProtectionCacheAware
---

## -description

The **ExReInitializeRundownProtectionCacheAware** routine reinitializes an **EX_RUNDOWN_REF_CACHE_AWARE** structure after the associated object is run down.

## -parameters

### -param RunRefCacheAware [in, out]

A pointer to a **EX_RUNDOWN_REF_CACHE_AWARE** structure that was initialized by a previous call to [**ExAllocateCacheAwareRundownProtection**](./nf-wdm-exallocatecacheawarerundownprotection.md) or  [**ExInitializeRundownProtectionCacheAware**](./nf-wdm-exinitializerundownprotectioncacheaware.md). The cache-aware run-down protection routines use this structure to track the run-down status of the associated shared object. This structure is opaque to drivers.

## -remarks

This routine is called by the driver that owns an object that resides in shared memory and that is accessed by other drivers.

**ExReInitializeRundownProtectionCacheAware** enables a previously used **EX_RUNDOWN_REF_CACHE_AWARE** structure to be associated with a new object, and initializes cache-aware run-down protection on this object. After the **ExReInitializeRundownProtectionCacheAware** call, drivers can call [**ExAcquireRundownProtectionCacheAware**](./nf-wdm-exacquirerundownprotectioncacheaware.md) to acquire cache-aware run-down protection on the new object.

An **ExReInitializeRundownProtectionCacheAware** call must be preceded by a call to the [**ExWaitForRundownProtectionReleaseCacheAware**](./nf-wdm-exwaitforrundownprotectionreleasecacheaware.md) routine that runs down the old object. Between the **ExWaitForRundownProtectionReleaseCacheAware** and **ExReInitializeRundownProtectionCacheAware** calls, the driver might call the [**ExRundownCompletedCacheAware**](./nf-wdm-exrundowncompletedcacheaware.md) routine to indicate that the run down of the old object has completed.

On entry, the status information in the **EX_RUNDOWN_REF_CACHE_AWARE** structure must indicate that the old object was run down. 

## -see-also

[Cache-aware run-down protection](/windows-hardware/drivers/kernel/run-down-protection#cache-aware-run-down-protection)

[**ExAcquireRundownProtectionCacheAware**](./nf-wdm-exacquirerundownprotectioncacheaware.md)

[**ExAcquireRundownProtectionCacheAwareEx**](./nf-wdm-exacquirerundownprotectioncacheawareex.md)

[**ExAllocateCacheAwareRundownProtection**](./nf-wdm-exallocatecacheawarerundownprotection.md)

[**ExFreeCacheAwareRundownProtection**](./nf-wdm-exfreecacheawarerundownprotection.md)

[**ExInitializeRundownProtectionCacheAware**](./nf-wdm-exinitializerundownprotectioncacheaware.md)

[**ExReleaseRundownProtectionCacheAware**](./nf-wdm-exreleaserundownprotectioncacheaware.md)

[**ExReleaseRundownProtectionCacheAwareEx**](./nf-wdm-exreleaserundownprotectioncacheawareex.md)

[**ExRundownCompletedCacheAware**](./nf-wdm-exrundowncompletedcacheaware.md)

[**ExSizeOfRundownProtectionCacheAware**](./nf-wdm-exsizeofrundownprotectioncacheaware.md)

[**ExWaitForRundownProtectionReleaseCacheAware**](./nf-wdm-exwaitforrundownprotectionreleasecacheaware.md)
