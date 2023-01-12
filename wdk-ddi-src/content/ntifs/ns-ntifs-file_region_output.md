---
UID: NS:ntifs._FILE_REGION_OUTPUT
tech.root: ifsk
title: FILE_REGION_OUTPUT
ms.date: 10/18/2022
targetos: Windows
description: Learn more about the FILE_REGION_OUTPUT structure.
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
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: FILE_REGION_OUTPUT, *PFILE_REGION_OUTPUT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_REGION_OUTPUT
 - PFILE_REGION_OUTPUT
 - FILE_REGION_OUTPUT
f1_keywords:
 - _FILE_REGION_OUTPUT
 - ntifs/_FILE_REGION_OUTPUT
 - PFILE_REGION_OUTPUT
 - ntifs/PFILE_REGION_OUTPUT
 - FILE_REGION_OUTPUT
 - ntifs/FILE_REGION_OUTPUT
dev_langs:
 - c++
helpviewer_keywords:
 - _FILE_REGION_OUTPUT
---

## -description

**FILE_REGION_OUTPUT** is the output structure for [**FSCTL_QUERY_FILE_REGIONS**](ni-ntifs-fsctl_query_file_regions.md).

## -struct-fields

### -field Flags

A 32-bit unsigned integer that indicates the flags for this operation. No flags are currently defined so this field should be set to zero and be ignored.

### -field TotalRegionEntryCount

A 32-bit unsigned integer that indicates the total number of regions that could be returned.

### -field RegionEntryCount

A 32-bit unsigned integer that indicates the number of regions that were actually returned and which are contained in this structure.

### -field Reserved

Reserved; this field should be set to zero and ignored.

### -field Region[1]

One or more [**FILE_REGION_INFO**](ns-ntifs-file_region_info.md) structures that contain information on the desired ranges based on the desired usage indicated by [**DesiredUsage**](ns-ntifs-file_region_input.md).

## -remarks

## -see-also

[**FILE_REGION_INFO**](ns-ntifs-file_region_info.md)

[**FILE_REGION_INPUT**](ns-ntifs-file_region_input.md)

[**FSCTL_QUERY_FILE_REGIONS**](ni-ntifs-fsctl_query_file_regions.md)
