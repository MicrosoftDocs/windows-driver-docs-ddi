---
UID: NS:ntifs.FIND_BY_SID_OUTPUT
tech.root: ifsk
title: FIND_BY_SID_OUTPUT
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FIND_BY_SID_OUTPUT structure.
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
req.typenames: FIND_BY_SID_OUTPUT, *PFIND_BY_SID_OUTPUT
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
 - FIND_BY_SID_OUTPUT
 - PFIND_BY_SID_OUTPUT
f1_keywords:
 - FIND_BY_SID_OUTPUT
 - ntifs/FIND_BY_SID_OUTPUT
 - PFIND_BY_SID_OUTPUT
 - ntifs/PFIND_BY_SID_OUTPUT
dev_langs:
 - c++
helpviewer_keywords:
 - FIND_BY_SID_OUTPUT
---

## -description

The **FIND_BY_SID_OUTPUT** structure represents the fully qualified path name of a file found by the [**FSCTL_FIND_FILES_BY_SID**](ni-ntifs-fsctl_find_files_by_sid.md) control code.

## -struct-fields

### -field NextEntryOffset

Number of bytes that must be skipped to get to the next record. A value of zero indicates that this is the last record.

### -field FileIndex

Index of the file.

### -field FileNameLength

The size of the file name, in bytes. This size does not include the NULL character.

### -field FileName[1]

A null-terminated string that specifies the file name.

## -remarks

## -see-also

[**FSCTL_FIND_FILES_BY_SID**](ni-ntifs-fsctl_find_files_by_sid.md)
