---
UID: NS:ntifs._FILE_LEVEL_TRIM_RANGE
title: _FILE_LEVEL_TRIM_RANGE (ntifs.h)
description: Contains the offset and length of a trim range for a file.
old-location: ifsk\file_level_trim_range.htm
tech.root: ifsk
ms.assetid: C74E90C5-9876-4CD1-B9A7-1B32A6AAB474
ms.date: 04/16/2018
keywords: ["FILE_LEVEL_TRIM_RANGE structure"]
ms.keywords: "*PFILE_LEVEL_TRIM_RANGE, FILE_LEVEL_TRIM_RANGE, FILE_LEVEL_TRIM_RANGE structure [Installable File System Drivers], PFILE_LEVEL_TRIM_RANGE, PFILE_LEVEL_TRIM_RANGE structure pointer [Installable File System Drivers], _FILE_LEVEL_TRIM_RANGE, ifsk.file_level_trim_range, ntifs/FILE_LEVEL_TRIM_RANGE, ntifs/PFILE_LEVEL_TRIM_RANGE"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: FILE_LEVEL_TRIM_RANGE, *PFILE_LEVEL_TRIM_RANGE
f1_keywords:
 - _FILE_LEVEL_TRIM_RANGE
 - ntifs/_FILE_LEVEL_TRIM_RANGE
 - PFILE_LEVEL_TRIM_RANGE
 - ntifs/PFILE_LEVEL_TRIM_RANGE
 - FILE_LEVEL_TRIM_RANGE
 - ntifs/FILE_LEVEL_TRIM_RANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FILE_LEVEL_TRIM_RANGE
---

# _FILE_LEVEL_TRIM_RANGE structure


## -description

Contains the offset and length of a trim range for a file.

## -struct-fields

### -field Offset

Byte offset from the front of the given file to trim at.

### -field Length

Length in bytes to trim from the given offset.

## -remarks

Due to alignment requirements, the file system may reduce the of the trim range to a multiple of <b>PAGE_SIZE</b> <= <b>Length</b>. Also, <b>Offset</b> will be adjusted to the next page boundary if its initial value is not on page boundary.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_level_trim">FILE_LEVEL_TRIM</a>