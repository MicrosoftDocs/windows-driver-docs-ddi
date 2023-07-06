---
UID: NF:ntifs.CcSetAdditionalCacheAttributesEx
title: CcSetAdditionalCacheAttributesEx function (ntifs.h)
description: Learn more about the CcSetAdditionalCacheAttributesEx routine.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["CcSetAdditionalCacheAttributesEx function"]
ms.keywords: CcSetAdditionalCacheAttributesEx, ifsk.ccsetadditionalcacheattributesex, ntifs/CcSetAdditionalCacheAttributesEx
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - CcSetAdditionalCacheAttributesEx
 - ntifs/CcSetAdditionalCacheAttributesEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcSetAdditionalCacheAttributesEx
---

# CcSetAdditionalCacheAttributesEx function

## -description

Call the **CcSetAdditionalCacheAttributesEx** routine to enable extended cache behavior on a cached file.

## -parameters

### -param FileObject [in]

Pointer to a file object for the cached file.

### -param Flags [in]

Behavior flags to set for **FileObject**. Currently, only the  **AGGRESSIVE_UNMAP_BEHIND** flag is available. Setting this flag will allow the cache manager to optimize memory usage when modified writes are disabled for a file object.

## -remarks

**CcSetAdditionalCacheAttributesEx** can be called any time after calling [**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md).

## -see-also

[**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md)

[**CcSetAdditionalCacheAttributes**](nf-ntifs-ccsetadditionalcacheattributes.md)
