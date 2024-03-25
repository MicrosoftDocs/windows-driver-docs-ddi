---
UID: NF:wdm.ExRundownCompletedCacheAware
tech.root: kernel
title: ExRundownCompletedCacheAware (wdm.h)
ms.date: 02/22/2024
targetos: Windows
description: This topic describes the ExRundownCompletedCacheAware function.
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
 - ExRundownCompletedCacheAware
f1_keywords:
 - ExRundownCompletedCacheAware
 - wdm/ExRundownCompletedCacheAware
dev_langs:
 - c++
helpviewer_keywords:
 - ExRundownCompletedCacheAware
---

## -description

The **ExRundownCompletedCacheAware** routine updates the run-down status of a shared object to indicate that the run down of the object has completed.

## -parameters

### -param RunRefCacheAware [in, out]

Pointer to the rundown protection object that the function will operate on. This is a pointer to an opaque **EX_RUNDOWN_REF_CACHE_AWARE** structure returned by a previous call to [**ExAllocateCacheAwareRundownProtection**](./nf-wdm-exallocatecacheawarerundownprotection.md) or [**ExInitializeRundownProtectionCacheAware**](./nf-wdm-exinitializerundownprotectioncacheaware.md).

## -remarks

This routine is called by the driver that owns an object that resides in shared memory and that is accessed by other drivers. The **ExRundownCompletedCacheAware** call must be preceded by a call to the [**ExWaitForRundownProtectionReleaseCacheAware**](./nf-wdm-exwaitforrundownprotectionreleasecacheaware.md) routine that runs down the object.

After an **ExRundownCompletedCacheAware** call, additional calls to [**ExWaitForRundownProtectionReleaseCacheAware**](/windows-hardware/drivers/ddi/wdm/nf-wdm-exwaitforrundownprotectionreleasecacheaware) to run down the associated object return immediately without waiting. However, calls to [**ExAcquireRundownProtectionCacheAware**](./nf-wdm-exacquirerundownprotectioncacheaware.md) to acquire run-down protection on the associated object fail (return <b>FALSE</b>).

After an **ExRundownCompletedCacheAware** call, the driver can call the [**ExReInitializeRundownProtectionCacheAware**](./nf-wdm-exreinitializerundownprotectioncacheaware.md) routine to associate the **EX_RUNDOWN_REF_CACHE_AWARE** structure with a new object and to initialize run-down protection on this object. After the **ExReInitializeRundownProtection** call, drivers can call [**ExAcquireRundownProtectionCacheAware**](./nf-wdm-exacquirerundownprotectioncacheaware.md) to acquire run-down protection on the new object.

On entry, the status information in the **EX_RUNDOWN_REF_CACHE_AWARE** structure must indicate that the object that was associated with this structure was run down. 

## -see-also

[Cache-aware run-down protection](/windows-hardware/drivers/kernel/run-down-protection#cache-aware-run-down-protection)

[**ExAcquireRundownProtectionCacheAware**](./nf-wdm-exacquirerundownprotectioncacheaware.md)

[**ExAcquireRundownProtectionCacheAwareEx**](./nf-wdm-exacquirerundownprotectioncacheawareex.md)

[**ExAllocateCacheAwareRundownProtection**](./nf-wdm-exallocatecacheawarerundownprotection.md)

[**ExFreeCacheAwareRundownProtection**](./nf-wdm-exfreecacheawarerundownprotection.md)

[**ExInitializeRundownProtectionCacheAware**](./nf-wdm-exinitializerundownprotectioncacheaware.md)

[**ExReInitializeRundownProtectionCacheAware**](./nf-wdm-exreinitializerundownprotectioncacheaware.md)

[**ExReleaseRundownProtectionCacheAware**](./nf-wdm-exreleaserundownprotectioncacheaware.md)

[**ExReleaseRundownProtectionCacheAwareEx**](./nf-wdm-exreleaserundownprotectioncacheawareex.md)

[**ExSizeOfRundownProtectionCacheAware**](./nf-wdm-exsizeofrundownprotectioncacheaware.md)

[**ExWaitForRundownProtectionReleaseCacheAware**](./nf-wdm-exwaitforrundownprotectionreleasecacheaware.md)
