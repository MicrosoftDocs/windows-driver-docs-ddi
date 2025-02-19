---
UID: NS:ntifs.MFT_ENUM_DATA_V1
tech.root: ifsk
title: MFT_ENUM_DATA_V1
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the MFT_ENUM_DATA_V1 structure.
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
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: 
req.target-type: 
req.typenames: MFT_ENUM_DATA_V1, *PMFT_ENUM_DATA_V1
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
 - MFT_ENUM_DATA_V1
 - PMFT_ENUM_DATA_V1
f1_keywords:
 - MFT_ENUM_DATA_V1
 - ntifs/MFT_ENUM_DATA_V1
 - PMFT_ENUM_DATA_V1
 - ntifs/PMFT_ENUM_DATA_V1
dev_langs:
 - c++
helpviewer_keywords:
 - MFT_ENUM_DATA_V1
---

## -description

The **MFT_ENUM_DATA_V1** structure contains information defining the boundaries for and starting place of an enumeration of update sequence number (USN) change journal records for ReFS volumes. It is used as the input buffer for the [**FSCTL_ENUM_USN_DATA**](ni-ntifs-fsctl_enum_usn_data.md) control code.

## -struct-fields

### -field StartFileReferenceNumber

The ordinal position within the files on the current volume at which the enumeration is to begin.

The first call to **FSCTL_ENUM_USN_DATA** during an enumeration must have the **StartFileReferenceNumber** member set to (DWORDLONG)0. Each call to **FSCTL_ENUM_USN_DATA** retrieves the starting point for the subsequent call as the first entry in the output buffer. Subsequent calls must be made with **StartFileReferenceNumber** set to this value.

### -field LowUsn

The lower boundary of the range of USN values used to filter which records are returned. Only records whose last change journal USN is between or equal to the LowUsn and HighUsn member values are returned.

### -field HighUsn

The upper boundary of the range of USN values used to filter which files are returned.

### -field MinMajorVersion

The minimum supported major version for the USN change journal.

### -field MaxMajorVersion

The maximum supported major version for the USN change journal.

| Value | Meaning |
| ----- | ------- |
| 2 | The data returned from FSCTL_ENUM_USN_DATA will contain USN_RECORD_V2 structures. |
| 3 | The data returned from FSCTL_ENUM_USN_DATA will contain USN_RECORD_V2 or USN_RECORD_V3 structures. |

## -see-also

[**FSCTL_ENUM_USN_DATA**](ni-ntifs-fsctl_enum_usn_data.md)
