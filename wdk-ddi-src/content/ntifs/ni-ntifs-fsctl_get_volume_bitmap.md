---
UID: NI:ntifs.FSCTL_GET_VOLUME_BITMAP
tech.root: ifsk
title: FSCTL_GET_VOLUME_BITMAP
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FSCTL_GET_VOLUME_BITMAP control code.
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
 - FSCTL_GET_VOLUME_BITMAP
f1_keywords:
 - FSCTL_GET_VOLUME_BITMAP
 - ntifs/FSCTL_GET_VOLUME_BITMAP
dev_langs:
 - c++
helpviewer_keywords:
 - FSCTL_GET_VOLUME_BITMAP
---

## -description

The **FSCTL_GET_VOLUME_BITMAP** control code retrieves a bitmap of occupied and available clusters on a volume.

## -ioctlparameters

### -ioctl-major-code

FSCTL_GET_VOLUME_BITMAP

### -input-buffer

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

## -remarks

To perform this operation, call [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md).

See [FSCTL_GET_VOLUME_BITMAP IOCTL (winioctl.h)](/windows/win32/api/winioctl/ni-winioctl-fsctl_get_volume_bitmap).

## -see-also

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md)

[**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md)

[**VOLUME_BITMAP_BUFFER**](ns-ntifs-volume_bitmap_buffer.md)

[**STARTING_LCN_INPUT_BUFFER**](ns-ntifs-starting_lcn_input_buffer.md)
