---
UID: NF:ntifs.CcGetFileSizePointer
tech.root: ifsk
title: CcGetFileSizePointer
ms.date: 09/27/2023
targetos: Windows
description: Learn more about the CcGetFileSizePointer function.
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
req.target-min-winverclnt: 
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
 - CcGetFileSizePointer
f1_keywords:
 - CcGetFileSizePointer
 - ntifs/CcGetFileSizePointer
dev_langs:
 - c++
helpviewer_keywords:
 - CcGetFileSizePointer
---

## -description

**CcGetFileSizePointer** returns the size of a file.

## -parameters

### -param FO

[in] Pointer to a file object for the file whose size is to be returned.

## -remarks

The **CcGetFileSizePointer** macro returns a pointer to a member of the cache manager structure for this file that specifies the file size in bytes.

## -see-also

[**CcSetFileSizes**](nf-ntifs-ccsetfilesizes.md)
