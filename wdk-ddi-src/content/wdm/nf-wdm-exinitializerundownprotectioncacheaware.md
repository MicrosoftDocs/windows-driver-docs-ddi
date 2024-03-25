---
UID: NF:wdm.ExInitializeRundownProtectionCacheAware
tech.root: kernel
title: ExInitializeRundownProtectionCacheAware (wdm.h)
ms.date: 02/16/2024
targetos: Windows
description: This topic describes the ExInitializeRundownProtectionCacheAware function.
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
 - ExInitializeRundownProtectionCacheAware
f1_keywords:
 - ExInitializeRundownProtectionCacheAware
 - wdm/ExInitializeRundownProtectionCacheAware
dev_langs:
 - c++
helpviewer_keywords:
 - ExInitializeRundownProtectionCacheAware
---

## -description

This routine initializes a cache-aware rundown protection object.

## -parameters

### -param RunRefCacheAware [out]

Pointer to a caller-supplied buffer where the routine returns an opaque **EX_RUNDOWN_REF_CACHE_AWARE** structure. See Remarks for more information.

### -param RunRefSize [in]

Specifies the size, in bytes, of the rundown protection object.

## -remarks

Rundown protection is a synchronization mechanism used by the Windows kernel to safely clean up resources that might be accessed by multiple threads.

This function is optimized for scenarios where the access patterns to a protected resource are cache-aware, meaning that the same thread is likely to access the resource repeatedly, and different threads are likely to access different parts of the resource. By using this function rather than ExInitializeRundownProtection, a driver can reduce the likelihood of cache contention, where multiple threads compete for the same cache lines, leading to performance degradation.

This function is typically used during the initialization phase of a driver, when it is setting up the resources that it needs to operate. The driver calls this function for each resource that needs to be protected by cache-aware rundown protection.

The **EX_RUNDOWN_REF_CACHE_AWARE** structure is an opaque structure that is used to manage the rundown protection. The caller should first call [**ExSizeOfRundownProtectionCacheAware**](./nf-wdm-exsizeofrundownprotectioncacheaware.md) to determine the appropriate size for the rundown protection object. This size should then be used to allocate a buffer for the **RunRefCacheAware** parameter and also passed as the **RunRefSize** parameter.

## -see-also

[**ExAcquireRundownProtectionCacheAware**](./nf-wdm-exacquirerundownprotectioncacheaware.md)

[**ExAcquireRundownProtectionCacheAwareEx**](./nf-wdm-exacquirerundownprotectioncacheawareex.md)

[**ExAllocateCacheAwareRundownProtection**](./nf-wdm-exallocatecacheawarerundownprotection.md)

[**ExFreeCacheAwareRundownProtection**](./nf-wdm-exfreecacheawarerundownprotection.md)

[**ExReInitializeRundownProtectionCacheAware**](./nf-wdm-exreinitializerundownprotectioncacheaware.md)

[**ExReleaseRundownProtectionCacheAware**](./nf-wdm-exreleaserundownprotectioncacheaware.md)

[**ExReleaseRundownProtectionCacheAwareEx**](./nf-wdm-exreleaserundownprotectioncacheawareex.md)

[**ExRundownCompletedCacheAware**](./nf-wdm-exrundowncompletedcacheaware.md)

[**ExSizeOfRundownProtectionCacheAware**](./nf-wdm-exsizeofrundownprotectioncacheaware.md)

[**ExWaitForRundownProtectionReleaseCacheAware**](./nf-wdm-exwaitforrundownprotectionreleasecacheaware.md)

[Cache-aware run-down protection](/windows-hardware/drivers/kernel/run-down-protection#cache-aware-run-down-protection)
