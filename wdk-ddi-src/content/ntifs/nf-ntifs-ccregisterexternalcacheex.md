---
UID: NF:ntifs.CcRegisterExternalCacheEx
tech.root: ifsk
title: CcRegisterExternalCacheEx
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the CcRegisterExternalCacheEx function.
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
 - CcRegisterExternalCacheEx
f1_keywords:
 - CcRegisterExternalCacheEx
 - ntifs/CcRegisterExternalCacheEx
dev_langs:
 - c++
helpviewer_keywords:
 - CcRegisterExternalCacheEx
---

## -description

The **CcRegisterExternalCacheEx** routine registers an external cache with the cache manager.

## -parameters

### -param FileObject

[in] Pointer to a file object. **FileObject** is used to identify the volume associated with the external cache being registered.

### -param Callback

[in] A caller-implemented [**PEXTERNAL_CACHE_CALLBACK_EX**](nc-ntifs-pexternal_cache_callback_ex.md) callback routine that the cache manager will call on every lazy write scan.

### -param ExternalCacheContext

[out] Pointer to the context that identifies the external cache instance.

## -returns

**CcRegisterExternalCacheEx** returns STATUS_SUCCESS if the external cache is successfully registered. Otherwise, it returns an appropriate error code, such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_NOT_SUPPORTED | The cache manager's per-volume lazywriter isn't enabled. In this case, the caller is expected to fall back on traditional cache management. |

## -remarks

**CcRegisterExternalCacheEx** is the entry point for file systems (clients) to request registration of an external cache with the cache manager. The cache manager allocates an internal structure to represent this instance and add the callback routine provided by the caller. Cache manager will call the callback on every lazy write scan.

## -see-also

[**CcUpdateExternalCacheInfoEx**](nf-ntifs-ccupdateexternalcacheinfoex.md)

[**CcUnregisterExternalCacheEx**](nf-ntifs-ccunregisterexternalcacheex.md)
