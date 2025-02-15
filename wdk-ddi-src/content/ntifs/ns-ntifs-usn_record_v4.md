---
UID: NS:ntifs.USN_RECORD_V4
tech.root: ifsk
title: USN_RECORD_V4
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the USN_RECORD_V4 structure.
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
req.typenames: USN_RECORD_V4, *PUSN_RECORD_V4
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
 - USN_RECORD_V4
 - PUSN_RECORD_V4
f1_keywords:
 - USN_RECORD_V4
 - ntifs/USN_RECORD_V4
 - PUSN_RECORD_V4
 - ntifs/PUSN_RECORD_V4
dev_langs:
 - c++
helpviewer_keywords:
 - USN_RECORD_V4
---

## -description

The **USN_RECORD_V4** structure contains the information for an update sequence number (USN) change journal version 4.0 record. The version 2.0 record is defined by the [**USN_RECORD_V2**](ns-ntifs-usn_record_v2.md) structure (also called **USN_RECORD** structure). See [USN_RECORD_V4 structure (winioctl.h)](/windows/win32/api/winioctl/ns-winioctl-usn_record_v4) for details.

## -struct-fields

### -field Header

### -field FileReferenceNumber

### -field ParentFileReferenceNumber

### -field Usn

### -field Reason

### -field SourceInfo

### -field RemainingExtents

### -field NumberOfExtents

### -field ExtentSize

### -field Extents[1]

## -remarks

## -see-also

[**FSCTL_READ_USN_JOURNAL**](ni-ntifs-fsctl_read_usn_journal.md)
