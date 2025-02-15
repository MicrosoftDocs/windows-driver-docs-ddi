---
UID: NI:ntifs.FSCTL_MOVE_FILE
tech.root: ifsk
title: FSCTL_MOVE_FILE
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FSCTL_MOVE_FILE control code.
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
 - FSCTL_MOVE_FILE
f1_keywords:
 - FSCTL_MOVE_FILE
 - ntifs/FSCTL_MOVE_FILE
dev_langs:
 - c++
helpviewer_keywords:
 - FSCTL_MOVE_FILE
---

## -description

The **FSCTL_MOVE_FILE** control code relocates one or more virtual clusters of a file from one logical cluster to another within the same volume.

## -ioctlparameters

### -ioctl-major-code

FSCTL_MOVE_FILE

### -input-buffer

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

## -remarks

To perform this operation, call [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md).

See [FSCTL_MOVE_FILE IOCTL (winioctl.h)](/windows/win32/api/winioctl/ni-winioctl-fsctl_move_file) for more information.

## -see-also

[**MOVE_FILE_DATA**](ns-ntifs-move_file_data.md)

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md)

[**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md)
