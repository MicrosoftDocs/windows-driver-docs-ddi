---
UID: NC:ntifs.PEXTERNAL_CACHE_CALLBACK_EX
tech.root: ifsk
title: PEXTERNAL_CACHE_CALLBACK_EX
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the PEXTERNAL_CACHE_CALLBACK_EX callback function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - ntifs.h
api_name:
 - PEXTERNAL_CACHE_CALLBACK_EX
f1_keywords:
 - PEXTERNAL_CACHE_CALLBACK_EX
 - ntifs/PEXTERNAL_CACHE_CALLBACK_EX
dev_langs:
 - c++
helpviewer_keywords:
 - PEXTERNAL_CACHE_CALLBACK_EX
---

## -description

The **PEXTERNAL_CACHE_CALLBACK_EX** callback function is called by the cache manager (*Cc*) on every lazy write scan.

## -parameters

### -param ExternalCacheContext

[in] Pointer to the context that identifies the external cache structure. This context was returned by [**CcRegisterExternalCacheEx**](nf-ntifs-ccregisterexternalcacheex.md).

### -param DirtyPagesInfo

[in] Pointer to a [**CC_DIRTY_PAGES_INFO**](ns-ntifs-cc_dirty_pages_info.md) structure that contains information about dirty page statistics for the external cache.

## -remarks

A client (file system) must register an external cache with *Cc* by calling [**CcRegisterExternalCacheEx**](nf-ntifs-ccregisterexternalcacheex.md) before it can receive callbacks from *Cc* during lazy write scans.

The values in **DirtyPagesInfo** are provided by the *Cc* to the external cache client through this callback routine.

Targets (**DirtyPageTarget** and **CleanLockedCachedPagesTarget**) are for defining the upper limits. The client must strive to keep these metrics at or under their target value. When targets are exceeded, the client needs to aggressively bring down the corresponding metric.

Thresholds (**DirtyPageThreshold** and **CleanLockedCachedPagesThreshold**) define the hard upper limit that a client must not cross. The client must therefore pause all activities that could cause thresholds to be exceeded.

## -see-also

[**CcRegisterExternalCacheEx**](nf-ntifs-ccregisterexternalcacheex.md)

[**CC_DIRTY_PAGES_INFO**](ns-ntifs-cc_dirty_pages_info.md)
