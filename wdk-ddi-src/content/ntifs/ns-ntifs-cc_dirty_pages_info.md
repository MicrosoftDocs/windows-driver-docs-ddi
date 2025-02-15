---
UID: NS:ntifs._CC_DIRTY_PAGES_INFO
tech.root: ifsk
title: CC_DIRTY_PAGES_INFO
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the CC_DIRTY_PAGES_INFO structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: CC_DIRTY_PAGES_INFO, *PCC_DIRTY_PAGES_INFO
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _CC_DIRTY_PAGES_INFO
 - PCC_DIRTY_PAGES_INFO
 - CC_DIRTY_PAGES_INFO
f1_keywords:
 - _CC_DIRTY_PAGES_INFO
 - ntifs/_CC_DIRTY_PAGES_INFO
 - PCC_DIRTY_PAGES_INFO
 - ntifs/PCC_DIRTY_PAGES_INFO
 - CC_DIRTY_PAGES_INFO
 - ntifs/CC_DIRTY_PAGES_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - _CC_DIRTY_PAGES_INFO
---

## -description

The **CC_DIRTY_PAGES_INFO** structure contains information about dirty page statistics for an external cache.

## -struct-fields

### -field Version

The version of the **CC_DIRTY_PAGES_INFO** structure. This field must be set to **CC_DIRTY_PAGES_INFO_V1**.

### -field DirtyPageThreshold

The hard upper limit for dirty pages. The Cache Manager (*Cc*) provides this value to the external cache client.

The external cache client must not exceed this limit and should pause activities that could increase dirty pages beyond this threshold.

### -field DirtyPageTarget

The target limit for dirty pages. *Cc* provides this value to the external cache client.

The external cache client should strive to keep the number of dirty pages at or below this value.

### -field CleanLockedCachedPagesThreshold

The hard upper limit for clean locked cached pages. *Cc* provides this value to the external cache client.

The external cache client must not exceed this limit.

### -field CleanLockedCachedPagesTarget

The target limit for clean locked cached pages. *Cc* provides this value to the external cache client.

The external cache client should aim to maintain the number of clean locked cached pages at or below this value.

### -field CurrentDirtyPages

The current number of dirty pages reported by the external cache client back to the *Cc*. Must be zero when passed from *Cc* to the external cache client's callback.

### -field CurrentCleanLockedCachedPages

The current number of clean locked cached pages reported by the external cache client back to *Cc*. Must be zero when passed from *Cc* to the external cache client's callback.

### -field CurrentPagesQueuedForWriting

The current number of pages queued for writing, reported by the external cache client back to *Cc*. Must be zero when passed from *Cc* to the external cache client's callback.

## -remarks

The **CC_DIRTY_PAGES_INFO** structure facilitates communication between *Cc* and an external cache client regarding the management of dirty pages and clean locked cached pages.

*Cc* provides threshold and target values to the external cache client to guide the client's management strategies.

The external cache client reports back current metrics to *Cc*.

## -see-also

[**CcUpdateExternalCacheInfoEx**](nf-ntifs-ccupdateexternalcacheinfoex.md)

[**PEXTERNAL_CACHE_CALLBACK_EX**](nc-ntifs-pexternal_cache_callback_ex.md)
