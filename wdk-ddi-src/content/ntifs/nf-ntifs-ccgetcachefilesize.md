---
UID: NF:ntifs.CcGetCacheFileSize
tech.root: ifsk
title: CcGetCacheFileSize
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the CcGetCacheFileSize function.
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
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - ntifs.h
api_name:
 - CcGetCacheFileSize
f1_keywords:
 - CcGetCacheFileSize
 - ntifs/CcGetCacheFileSize
dev_langs:
 - c++
helpviewer_keywords:
 - CcGetCacheFileSize
---

## -description

The **CcGetCacheFileSize** function retrieves the current size of a file as known to the cache manager.

## -parameters

### -param SectionObjectPointer [in]

Pointer to a [**SECTION_OBJECT_POINTERS**](../wdm/ns-wdm-_section_object_pointers.md) structure that contains the section object information.

## -returns

**CcGetCacheFileSize** returns a 64-bit value that indicates the current file size.

## -see-also

[**CcSetCacheFileSizes**](nf-ntifs-ccsetcachefilesizes.md)
