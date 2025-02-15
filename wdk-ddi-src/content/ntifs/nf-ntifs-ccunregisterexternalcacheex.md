---
UID: NF:ntifs.CcUnregisterExternalCacheEx
tech.root: ifsk
title: CcUnregisterExternalCacheEx
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the CcUnregisterExternalCacheEx function.
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
 - CcUnregisterExternalCacheEx
f1_keywords:
 - CcUnregisterExternalCacheEx
 - ntifs/CcUnregisterExternalCacheEx
dev_langs:
 - c++
helpviewer_keywords:
 - CcUnregisterExternalCacheEx
---

## -description

**CcUnregisterExternalCacheEx** routine unregisters an external cache with the cache manager.

## -parameters

### -param ExternalCacheContext

[in] Pointer to the context that identifies the external cache to be unregistered. This context was returned by [**CcRegisterExternalCacheEx**](nf-ntifs-ccregisterexternalcacheex.md).

## -remarks

After a client (file system) unregisters an external cache, it will no longer receive any callbacks from the cache manager during lazy write scans.

## -see-also

[**CcRegisterExternalCacheEx**](nf-ntifs-ccregisterexternalcacheex.md)
