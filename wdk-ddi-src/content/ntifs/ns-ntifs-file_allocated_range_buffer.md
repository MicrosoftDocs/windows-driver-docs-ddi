---
UID: NS:ntifs._FILE_ALLOCATED_RANGE_BUFFER
tech.root: ifsk
title: FILE_ALLOCATED_RANGE_BUFFER
ms.date: 10/07/2022
targetos: Windows
description: Learn more about the FILE_ALLOCATED_RANGE_BUFFER structure.
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
req.target-min-winverclnt: Windows 2000
req.target-min-winversvr: 
req.target-type: 
req.typenames: FILE_ALLOCATED_RANGE_BUFFER, *PFILE_ALLOCATED_RANGE_BUFFER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_ALLOCATED_RANGE_BUFFER
 - PFILE_ALLOCATED_RANGE_BUFFER
 - FILE_ALLOCATED_RANGE_BUFFER
f1_keywords:
 - _FILE_ALLOCATED_RANGE_BUFFER
 - ntifs/_FILE_ALLOCATED_RANGE_BUFFER
 - PFILE_ALLOCATED_RANGE_BUFFER
 - ntifs/PFILE_ALLOCATED_RANGE_BUFFER
 - FILE_ALLOCATED_RANGE_BUFFER
 - ntifs/FILE_ALLOCATED_RANGE_BUFFER
dev_langs:
 - c++
helpviewer_keywords:
 - _FILE_ALLOCATED_RANGE_BUFFER
ms.custom: engagement-fy23
---

## -description

**FILE_ALLOCATED_RANGE_BUFFER** structures are used as input and output during a [**FSCTL_QUERY_ALLOCATED_RANGES**](ni-ntifs-fsctl_query_allocated_ranges.md) control code request.

## -struct-fields

### -field FileOffset

On FSCTL input, contains the file offset in bytes of the start of a range of bytes in a file. **FileOffset** must be greater than or equal to 0.

On FSCTL output, contains the file offset in bytes from the start of the file; the start of a range of bytes to which storage is allocated. If the file is a sparse file, **FileOffset** can contain ranges of bytes for which storage is not allocated; these ranges will be excluded from the list of allocated ranges returned by [**FSCTL_QUERY_ALLOCATED_RANGES**](ni-ntifs-fsctl_query_allocated_ranges.md). Because an application using a sparse file can choose whether or not to allocate disk space for each sequence of 0x00-valued bytes, the allocated ranges can contain 0x00-valued bytes. This value must be greater than or equal to 0 on output.

### -field Length

Contains the size in bytes of the range. On FSCTL input, **Length** must be greater than or equal to 0. On FSCTL output, **Length** must be greater than 0.

## -see-also

 [**FSCTL_QUERY_ALLOCATED_RANGES**](ni-ntifs-fsctl_query_allocated_ranges.md)