---
UID: NS:ntifs.USN_RECORD_V2
tech.root: ifsk
title: USN_RECORD_V2
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the USN_RECORD_V2 structure.
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
req.typenames: USN_RECORD_V2, *PUSN_RECORD_V2
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
 - USN_RECORD_V2
 - PUSN_RECORD_V2
f1_keywords:
 - USN_RECORD_V2
 - ntifs/USN_RECORD_V2
 - PUSN_RECORD_V2
 - ntifs/PUSN_RECORD_V2
dev_langs:
 - c++
helpviewer_keywords:
 - USN_RECORD_V2
---

## -description

The **USN_RECORD_V2** structure contains the information for an update sequence number (USN) change journal version 2.0 record. See [USN_RECORD_V2 structure (winioctl.h)](/windows/win32/api/winioctl/ns-winioctl-usn_record_v2) for details.

## -struct-fields

### -field RecordLength

### -field MajorVersion

### -field MinorVersion

### -field FileReferenceNumber

### -field ParentFileReferenceNumber

### -field Usn

### -field TimeStamp

### -field Reason

### -field SourceInfo

### -field SecurityId

### -field FileAttributes

### -field FileNameLength

### -field FileNameOffset

### -field FileName[1]

## -remarks

## -see-also

[**FSCTL_READ_USN_JOURNAL**](ni-ntifs-fsctl_read_usn_journal.md)
