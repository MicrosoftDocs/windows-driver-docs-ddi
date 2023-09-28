---
UID: NS:ntifs._CC_FILE_SIZES
tech.root: ifsk
title: CC_FILE_SIZES
ms.date: 09/27/2023
targetos: Windows
description: Learn more about the CC_FILE_SIZES structure.
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
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: CC_FILE_SIZES, *PCC_FILE_SIZES
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
 - _CC_FILE_SIZES
 - PCC_FILE_SIZES
 - CC_FILE_SIZES
f1_keywords:
 - _CC_FILE_SIZES
 - ntifs/_CC_FILE_SIZES
 - PCC_FILE_SIZES
 - ntifs/PCC_FILE_SIZES
 - CC_FILE_SIZES
 - ntifs/CC_FILE_SIZES
dev_langs:
 - c++
helpviewer_keywords:
 - _CC_FILE_SIZES
---

## -description

The **CC_FILE_SIZES** structure contains file size information.

## -struct-fields

### -field AllocationSize

The section object size for the file, in bytes.

### -field FileSize

The size of the file, in bytes.

### -field ValidDataLength

The valid date length for the file, in bytes.

## -see-also

[**CcSetFileSizes**](nf-ntifs-ccsetfilesizes.md)
