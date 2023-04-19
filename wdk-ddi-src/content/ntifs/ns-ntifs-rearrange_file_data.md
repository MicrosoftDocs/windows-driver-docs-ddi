---
UID: NS:ntifs._REARRANGE_FILE_DATA
tech.root: ifsk
title: REARRANGE_FILE_DATA
ms.date: 04/17/2023
targetos: Windows
description: Learn more about the REARRANGE_FILE_DATA structure.
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
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.target-type: 
req.typenames: REARRANGE_FILE_DATA, *PREARRANGE_FILE_DATA
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
 - _REARRANGE_FILE_DATA
 - PREARRANGE_FILE_DATA
 - REARRANGE_FILE_DATA
f1_keywords:
 - _REARRANGE_FILE_DATA
 - ntifs/_REARRANGE_FILE_DATA
 - PREARRANGE_FILE_DATA
 - ntifs/PREARRANGE_FILE_DATA
 - REARRANGE_FILE_DATA
 - ntifs/REARRANGE_FILE_DATA
dev_langs:
 - c++
helpviewer_keywords:
 - _REARRANGE_FILE_DATA
---

## -description

**REARRANGE_FILE_DATA** is the input structure for the [**FSCTL_REARRANGE_FILE**](ni-ntifs-fsctl_rearrange_file.md) control code.

## -struct-fields

### -field SourceStartingOffset

Cluster-aligned byte offset of the base of the contiguous source region in the source file to move to the target location of the target file.

### -field TargetOffset

Cluster-aligned byte offset of the point to insert the source region.

### -field SourceFileHandle

Handle to the alternate file to move the source region clusters from. This feature is not currently supported so **SourceFileHandle** must be set to NULL, which indicates that the source region is from the same file.

### -field Length

Cluster-aligned length in bytes of the source region.

### -field Flags

Reserved for future use; must be set to zero.

## -see-also

[**FSCTL_REARRANGE_FILE**](ni-ntifs-fsctl_rearrange_file.md)
