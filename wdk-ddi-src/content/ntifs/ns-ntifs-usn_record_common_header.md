---
UID: NS:ntifs.USN_RECORD_COMMON_HEADER
tech.root: ifsk
title: USN_RECORD_COMMON_HEADER
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the USN_RECORD_COMMON_HEADER structure.
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
req.typenames: USN_RECORD_COMMON_HEADER, *PUSN_RECORD_COMMON_HEADER
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
 - USN_RECORD_COMMON_HEADER
 - PUSN_RECORD_COMMON_HEADER
f1_keywords:
 - USN_RECORD_COMMON_HEADER
 - ntifs/USN_RECORD_COMMON_HEADER
 - PUSN_RECORD_COMMON_HEADER
 - ntifs/PUSN_RECORD_COMMON_HEADER
dev_langs:
 - c++
helpviewer_keywords:
 - USN_RECORD_COMMON_HEADER
---

## -description

The **USN_RECORD_COMMON_HEADER** structure contains the information for an update sequence number (USN) common header which is common through [**USN_RECORD_V2**](ns-ntifs-usn_record_v2.md), [**USN_RECORD_V3**](ns-ntifs-usn_record_v3.md) and [**USN_RECORD_V4**](ns-ntifs-usn_record_v4.md) structure.

## -struct-fields

### -field RecordLength

The total length of a record, in bytes.

Because USN record is a variable size, the **RecordLength** member should be used when calculating the address of the next record in an output buffer.

For [**USN_RECORD_V4**](ns-ntifs-usn_record_v4.md) structure, the size in bytes of any change journal record is at most the size of the structure, plus (NumberOfExtents-1) times size of the USN_RECORD_EXTENT.

### -field MajorVersion

The major version number of the change journal software for this record.

For example, if the change journal software is version 4.0, the major version number is 4.

| Value | Description |
| ----- | ----------- |
| 2     | The structure is a [**USN_RECORD_V2**](ns-ntifs-usn_record_v2.md) structure and the remainder of the structure should be parsed using that layout. |
| 3     | The structure is a [**USN_RECORD_V3**](ns-ntifs-usn_record_v3.md) structure and the remainder of the structure should be parsed using that layout. |
| 4     | The structure is a [**USN_RECORD_V4**](ns-ntifs-usn_record_v4.md) structure and the remainder of the structure should be parsed using that layout. |

### -field MinorVersion

The minor version number of the change journal software for this record. For example, if the change journal software is version 4.0, the minor version number is zero.

## -see-also

[**FSCTL_READ_USN_JOURNAL**](ni-ntifs-fsctl_read_usn_journal.md)
