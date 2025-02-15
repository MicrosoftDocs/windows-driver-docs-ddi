---
UID: NS:ntifs.USN_TRACK_MODIFIED_RANGES
tech.root: ifsk
title: USN_TRACK_MODIFIED_RANGES
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the USN_TRACK_MODIFIED_RANGES structure.
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
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.target-type: 
req.typenames: USN_TRACK_MODIFIED_RANGES, *PUSN_TRACK_MODIFIED_RANGES
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - USN_TRACK_MODIFIED_RANGES
 - PUSN_TRACK_MODIFIED_RANGES
f1_keywords:
 - USN_TRACK_MODIFIED_RANGES
 - ntifs/USN_TRACK_MODIFIED_RANGES
 - PUSN_TRACK_MODIFIED_RANGES
 - ntifs/PUSN_TRACK_MODIFIED_RANGES
dev_langs:
 - c++
helpviewer_keywords:
 - USN_TRACK_MODIFIED_RANGES
---

## -description

The **USN_TRACK_MODIFIED_RANGES** structure contains returned update sequence number (USN) from [**FSCTL_USN_TRACK_MODIFIED_RANGES**](ni-ntifs-fsctl_usn_track_modified_ranges.md) control code.

## -struct-fields

### -field Flags

Indicates enabling range tracking.

| Value | Description |
| ----- | ----------- |
| FLAG_USN_TRACK_MODIFIED_RANGES_ENABLE 0x00000001 | This flag is mandatory with FSCTL_USN_TR**ACK_MODIFIED_RANGES and is used to enable range tracking on the volume. |

### -field Unused

Reserved.

### -field ChunkSize

Chunk size for tracking ranges. A single byte modification will be reflected as the whole chunk being modified.

### -field FileSizeThreshold

File size threshold to start outputting [**USN_RECORD_V4**](ns-ntifs-usn_record_v4.md) structure record(s) for modified file, i.e. if the modified file size is less than this threshold, then no **USN_RECORD_V4** record will be output.

## -see-also

[**FSCTL_USN_TRACK_MODIFIED_RANGES**](ni-ntifs-fsctl_usn_track_modified_ranges.md)
