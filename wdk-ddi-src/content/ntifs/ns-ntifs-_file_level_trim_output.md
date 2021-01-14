---
UID: NS:ntifs._FILE_LEVEL_TRIM_OUTPUT
title: _FILE_LEVEL_TRIM_OUTPUT (ntifs.h)
description: The FILE_LEVEL_TRIM_OUTPUT structure contains the results of a trim operation performed by an FSCTL_FILE_LEVEL_TRIM request.
old-location: ifsk\file_level_trim_output.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FILE_LEVEL_TRIM_OUTPUT structure"]
ms.keywords: "*PFILE_LEVEL_TRIM_OUTPUT, FILE_LEVEL_TRIM_OUTPUT, FILE_LEVEL_TRIM_OUTPUT structure [Installable File System Drivers], FILE_LEVEL_TRIM_RANGE_OUTPUT, FILE_LEVEL_TRIM_RANGE_OUTPUT structure [Installable File System Drivers], PFILE_LEVEL_TRIM_RANGE_OUTPUT, PFILE_LEVEL_TRIM_RANGE_OUTPUT structure pointer [Installable File System Drivers], _FILE_LEVEL_TRIM_OUTPUT, ifsk.file_level_trim_output, ntifs/FILE_LEVEL_TRIM_RANGE, ntifs/PFILE_LEVEL_TRIM_RANGE_OUTPUT"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
req.typenames: FILE_LEVEL_TRIM_OUTPUT, *PFILE_LEVEL_TRIM_OUTPUT
f1_keywords:
 - _FILE_LEVEL_TRIM_OUTPUT
 - ntifs/_FILE_LEVEL_TRIM_OUTPUT
 - PFILE_LEVEL_TRIM_OUTPUT
 - ntifs/PFILE_LEVEL_TRIM_OUTPUT
 - FILE_LEVEL_TRIM_OUTPUT
 - ntifs/FILE_LEVEL_TRIM_OUTPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_LEVEL_TRIM_OUTPUT
 - PFILE_LEVEL_TRIM_OUTPUT
 - FILE_LEVEL_TRIM_OUTPUT
---

# _FILE_LEVEL_TRIM_OUTPUT structure


## -description

The <b>FILE_LEVEL_TRIM_OUTPUT</b> structure contains the results of a trim operation performed by an <a href="/windows-hardware/drivers/ifs/fsctl-file-level-trim">FSCTL_FILE_LEVEL_TRIM</a> request.

## -struct-fields

### -field NumRangesProcessed

The number or trim ranges processed.

## -remarks

This structure is optionally included as the output buffer for an <a href="/windows-hardware/drivers/ifs/fsctl-file-level-trim">FSCTL_FILE_LEVEL_TRIM</a> request. <b>NumRangesProcessed</b> indicates how many ranges of the in the array given in <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_level_trim">FILE_LEVEL_TRIM</a> were processed.

All trim ranges in the array in <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_level_trim">FILE_LEVEL_TRIM</a> were successfully processed if  <b>NumRangesProcessed</b> is equivalent to the <b>NumRanges</b> member of <b>FILE_LEVEL_TRIM</b>. Otherwise, the value in <b>NumRangesProcessed</b> is the starting index of the trim ranges that were not processed.

## -see-also

<a href="/windows-hardware/drivers/ifs/fsctl-file-level-trim">FSCTL_FILE_LEVEL_TRIM</a>

