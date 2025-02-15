---
UID: NS:ntifs.USN_RECORD_EXTENT
tech.root: ifsk
title: USN_RECORD_EXTENT
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the USN_RECORD_EXTENT structure.
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
req.typenames: USN_RECORD_EXTENT, *PUSN_RECORD_EXTENT
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
 - USN_RECORD_EXTENT
 - PUSN_RECORD_EXTENT
f1_keywords:
 - USN_RECORD_EXTENT
 - ntifs/USN_RECORD_EXTENT
 - PUSN_RECORD_EXTENT
 - ntifs/PUSN_RECORD_EXTENT
dev_langs:
 - c++
helpviewer_keywords:
 - USN_RECORD_EXTENT
---

## -description

The **USN_RECORD_EXTENT** structure contains the offset and length for an update sequence number (USN) record extent.

## -struct-fields

### -field Offset

The offset of the extent, in bytes.

### -field Length

The length of the extent, in bytes.

## -see-also

[**FSCTL_READ_USN_JOURNAL**](ni-ntifs-fsctl_read_usn_journal.md)

[**USN_RECORD_V4**](ns-ntifs-usn_record_v4.md)
