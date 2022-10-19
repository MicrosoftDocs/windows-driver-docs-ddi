---
UID: NS:ntifs._FILE_REGION_INFO
tech.root: ifsk
title: FILE_REGION_INFO
ms.date: 10/18/2022
targetos: Windows
description: Learn more about the FILE_REGION_INFO structure.
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
req.typenames: FILE_REGION_INFO, *PFILE_REGION_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_REGION_INFO
 - PFILE_REGION_INFO
 - FILE_REGION_INFO
f1_keywords:
 - _FILE_REGION_INFO
 - ntifs/_FILE_REGION_INFO
 - PFILE_REGION_INFO
 - ntifs/PFILE_REGION_INFO
 - FILE_REGION_INFO
 - ntifs/FILE_REGION_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - _FILE_REGION_INFO
---

## -description

The **FILE_REGION_INFO** structure contains a computed region of a file based on a desired usage. This structure is used to store region information for the [**FSCTL_QUERY_FILE_REGIONS**](ni-ntifs-fsctl_query_file_regions.md) reply message, with the [**FILE_REGION_OUTPUT**](ns-ntifs-file_region_output.md) structure containing one or more **FILE_REGION_INFO** structures.

## -struct-fields

### -field FileOffset

A 64-bit signed integer that contains the file offset, in bytes, of the region.

### -field Length

A 64-bit signed integer that contains the size, in bytes, of the region.

### -field Usage

A 32-bit unsigned integer that indicates the usage for the given region of the file. **Usage** can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| 0x00000000 | The given range is invalid. It does not match the criteria of the requested [**DesiredUsage**](ns-ntifs-file_region_input.md). |
| **FILE_USAGE_VALID_CACHED_DATA** (0x00000001) | Defines those regions of the file that exists before VDL as it exists in the cache manager. |
| **FILE_USAGE_VALID_NONCACHED_DATA** (0x00000002) | Defines those regions of the files that exist before VDL on the storage device. |

### -field Reserved

Reserved; this field should be set to zero and ignored.

## -remarks

## -see-also

[**FILE_REGION_INPUT**](ns-ntifs-file_region_input.md)

[**FILE_REGION_OUTPUT**](ns-ntifs-file_region_output.md)

[**FSCTL_QUERY_FILE_REGIONS**](ni-ntifs-fsctl_query_file_regions.md)