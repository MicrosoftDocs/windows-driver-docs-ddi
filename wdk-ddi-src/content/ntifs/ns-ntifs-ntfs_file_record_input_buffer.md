---
UID: NS:ntifs.NTFS_FILE_RECORD_INPUT_BUFFER
tech.root: ifsk
title: NTFS_FILE_RECORD_INPUT_BUFFER
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the NTFS_FILE_RECORD_INPUT_BUFFER structure.
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
req.typenames: NTFS_FILE_RECORD_INPUT_BUFFER, *PNTFS_FILE_RECORD_INPUT_BUFFER
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
 - NTFS_FILE_RECORD_INPUT_BUFFER
 - PNTFS_FILE_RECORD_INPUT_BUFFER
f1_keywords:
 - NTFS_FILE_RECORD_INPUT_BUFFER
 - ntifs/NTFS_FILE_RECORD_INPUT_BUFFER
 - PNTFS_FILE_RECORD_INPUT_BUFFER
 - ntifs/PNTFS_FILE_RECORD_INPUT_BUFFER
dev_langs:
 - c++
helpviewer_keywords:
 - NTFS_FILE_RECORD_INPUT_BUFFER
---

## -description

The **NTFS_FILE_RECORD_INPUT_BUFFER** structure is used with the [**FSCTL_GET_NTFS_FILE_RECORD**](ni-ntifs-fsctl_get_ntfs_file_record.md) control code.

## -struct-fields

### -field FileReferenceNumber

The file identifier of the file record to be retrieved. This is not necessarily the file identifier returned in the **FileReferenceNumber** member of the [**NTFS_FILE_RECORD_OUTPUT_BUFFER**](ns-ntifs-ntfs_file_record_output_buffer.md) structure.

## -see-also

[**FSCTL_GET_NTFS_FILE_RECORD**](ni-ntifs-fsctl_get_ntfs_file_record.md)

[**NTFS_FILE_RECORD_OUTPUT_BUFFER**](ns-ntifs-ntfs_file_record_output_buffer.md)
