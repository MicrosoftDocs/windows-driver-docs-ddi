---
UID: NF:ntifs.CcUpdateExternalCacheInfoEx
tech.root: ifsk
title: CcUpdateExternalCacheInfoEx
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the CcUpdateExternalCacheInfoEx function.
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
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - CcUpdateExternalCacheInfoEx
f1_keywords:
 - CcUpdateExternalCacheInfoEx
 - ntifs/CcUpdateExternalCacheInfoEx
dev_langs:
 - c++
helpviewer_keywords:
 - CcUpdateExternalCacheInfoEx
---

## -description

A file system calls **CcUpdateExternalCacheInfoEx** to ask the cache manager (*Cc*) to update dirty page statistics in the specified external cache information structure.

## -parameters

### -param ExternalCacheContext

[in] Pointer to the context that identifies the external cache structure to be updated. This context was returned by [**CcRegisterExternalCacheEx**](nf-ntifs-ccregisterexternalcacheex.md).

### -param DirtyPagesInfo

[in] Pointer to a [**CC_DIRTY_PAGES_INFO**](ns-ntifs-cc_dirty_pages_info.md) structure that contains updated information about dirty page statistics. *Cc* ignores the dirty page thresholds part of this structure.

## -returns

**CcUpdateExternalCacheInfoEx** returns STATUS_SUCCESS if the operation succeeds. Otherwise, it returns an appropriate error code such as the following.

| Return code | Description |
| ----------- | ----------- |
| STATUS_INVALID_PARAMETER | The version in **DirtyPagesInfo**  is invalid. |

## -remarks

*Cc* needs these updated values so it can accurately set the dirty page threshold and target.

## -see-also

[**CcRegisterExternalCacheEx**](nf-ntifs-ccregisterexternalcacheex.md)

[**CC_DIRTY_PAGES_INFO**](ns-ntifs-cc_dirty_pages_info.md)
