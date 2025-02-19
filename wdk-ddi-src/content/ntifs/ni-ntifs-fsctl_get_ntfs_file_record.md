---
UID: NI:ntifs.FSCTL_GET_NTFS_FILE_RECORD
tech.root: ifsk
title: FSCTL_GET_NTFS_FILE_RECORD
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FSCTL_GET_NTFS_FILE_RECORD control code.
prerelease: false
req.construct-type: ioctl
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FSCTL_GET_NTFS_FILE_RECORD
f1_keywords:
 - FSCTL_GET_NTFS_FILE_RECORD
 - ntifs/FSCTL_GET_NTFS_FILE_RECORD
dev_langs:
 - c++
helpviewer_keywords:
 - FSCTL_GET_NTFS_FILE_RECORD
---

## -description

The **FSCTL_GET_NTFS_FILE_RECORD** control code retrieves a file record from an NTFS volume.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

## -remarks

To perform this operation, call [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md).

See [**FSCTL_GET_NTFS_VOLUME_DATA**](/windows/win32/api/winioctl/ni-winioctl-fsctl_get_ntfs_file_record) for more information.

## -see-also

[**NTFS_FILE_RECORD_INPUT_BUFFER**](ns-ntifs-ntfs_file_record_input_buffer.md)

[**NTFS_FILE_RECORD_OUTPUT_BUFFER**](ns-ntifs-ntfs_file_record_output_buffer.md)
