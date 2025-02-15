---
UID: NS:ntifs.USN_RANGE_TRACK_OUTPUT
tech.root: ifsk
title: USN_RANGE_TRACK_OUTPUT
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the USN_RANGE_TRACK_OUTPUT structure.
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
req.typenames: USN_RANGE_TRACK_OUTPUT, *PUSN_RANGE_TRACK_OUTPUT
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
 - USN_RANGE_TRACK_OUTPUT
 - PUSN_RANGE_TRACK_OUTPUT
f1_keywords:
 - USN_RANGE_TRACK_OUTPUT
 - ntifs/USN_RANGE_TRACK_OUTPUT
 - PUSN_RANGE_TRACK_OUTPUT
 - ntifs/PUSN_RANGE_TRACK_OUTPUT
dev_langs:
 - c++
helpviewer_keywords:
 - USN_RANGE_TRACK_OUTPUT
---

## -description

The **USN_RANGE_TRACK_OUTPUT** structure contains returned update sequence number (USN) from the [**FSCTL_USN_TRACK_MODIFIED_RANGES**](ni-ntifs-fsctl_usn_track_modified_ranges.md) control code.

## -struct-fields

### -field Usn

Returned update sequence number (USN) that identifies at what point in the USN Journal that range tracking was enabled.

## -see-also

[**FSCTL_USN_TRACK_MODIFIED_RANGES**](ni-ntifs-fsctl_usn_track_modified_ranges.md)
