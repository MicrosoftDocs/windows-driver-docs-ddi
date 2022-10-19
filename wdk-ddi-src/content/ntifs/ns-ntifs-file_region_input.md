---
UID: NS:ntifs._FILE_REGION_INPUT
tech.root: ifsk
title: FILE_REGION_INPUT
ms.date: 10/18/2022
targetos: Windows
description: Learn more about the FILE_REGION_INPUT structure.
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
req.typenames: FILE_REGION_INPUT, *PFILE_REGION_INPUT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_REGION_INPUT
 - PFILE_REGION_INPUT
 - FILE_REGION_INPUT
f1_keywords:
 - _FILE_REGION_INPUT
 - ntifs/_FILE_REGION_INPUT
 - PFILE_REGION_INPUT
 - ntifs/PFILE_REGION_INPUT
 - FILE_REGION_INPUT
 - ntifs/FILE_REGION_INPUT
dev_langs:
 - c++
helpviewer_keywords:
 - _FILE_REGION_INPUT
---

## -description

**FILE_REGION_INPUT** is the optional input structure for [**FSCTL_QUERY_FILE_REGIONS**](ni-ntifs-fsctl_query_file_regions.md).

## -struct-fields

### -field FileOffset

A 64-bit signed integer that contains the file offset, in bytes, of the start of a range of bytes in a file.

### -field Length

A 64-bit signed integer that contains the size, in bytes, of the range.

### -field DesiredUsage

A 32-bit unsigned integer that indicates usage parameters for this operation. **DesiredUsage** can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| **FILE_REGION_USAGE_VALID_CACHED_DATA** (0x00000001) | Requests that information about the valid data length (VDL) for the specified file and file range in the cache be returned. |
| **FILE_REGION_USAGE_VALID_NONCACHED_DATA** (0x00000002) | Requests that information about the VDL for the specified file and file range on disk be returned. |
| All other values | If a **FILE_REGION_INPUT** object is specified in **FSCTL_QUERY_FILE_REGION**, then any other value will return STATUS_INVALID_PARAMETER. |

## -remarks

See [**FSCTL_QUERY_FILE_REGIONS**](ni-ntifs-fsctl_query_file_regions.md) for details.

## -see-also

[**FILE_REGION_OUTPUT**](ns-ntifs-file_region_output.md)

[**FSCTL_QUERY_FILE_REGIONS**](ni-ntifs-fsctl_query_file_regions.md)
