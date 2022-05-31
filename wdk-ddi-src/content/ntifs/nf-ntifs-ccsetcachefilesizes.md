---
UID: NF:ntifs.CcSetCacheFileSizes
tech.root: ifsk
title: CcSetCacheFileSizes
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the CcSetCacheFileSizes function.
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
 - CcSetCacheFileSizes
f1_keywords:
 - CcSetCacheFileSizes
 - ntifs/CcSetCacheFileSizes
dev_langs:
 - c++
helpviewer_keywords:
 - CcSetCacheFileSizes
---

## -description

The **CcSetCacheFileSizes** function sets the cache manager file sizes by section object pointers.

## -parameters

### -param SectionObjectPointer [in]

Pointer to a [**SECTION_OBJECT_POINTERS**](../wdm/ns-wdm-_section_object_pointers.md) structure that contains the section object information.

### -param FileSizes [in]

Pointer to a CC_FILE_SIZES structure that specifies the file size to set.

## -returns

## -remarks

The file system must ensure that the cache map is valid and will remain so for the duration of this call.

## -see-also

[**CcGetCacheFileSize**](nf-ntifs-ccgetcachefilesize.md)