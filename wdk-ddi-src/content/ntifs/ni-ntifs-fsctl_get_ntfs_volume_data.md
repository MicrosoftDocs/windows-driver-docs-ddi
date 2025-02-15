---
UID: NI:ntifs.FSCTL_GET_NTFS_VOLUME_DATA
tech.root: ifsk
title: FSCTL_GET_NTFS_VOLUME_DATA
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FSCTL_GET_NTFS_VOLUME_DATA control code.
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
 - FSCTL_GET_NTFS_VOLUME_DATA
f1_keywords:
 - FSCTL_GET_NTFS_VOLUME_DATA
 - ntifs/FSCTL_GET_NTFS_VOLUME_DATA
dev_langs:
 - c++
helpviewer_keywords:
 - FSCTL_GET_NTFS_VOLUME_DATA
---

## -description

The **FSCTL_GET_NTFS_VOLUME_DATA** control code retrieves information about the specified NTFS volume.

## -ioctlparameters

### -ioctl-major-code

FSCTL_GET_NTFS_VOLUME_DATA

### -input-buffer

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

## -remarks

To perform this operation, call [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md).

See [FSCTL_GET_NTFS_VOLUME_DATA IOCTL (winioctl.h)](/windows/win32/api/winioctl/ni-winioctl-fsctl_get_ntfs_volume_data) for more information.

## -see-also

[**NTFS_VOLUME_DATA_BUFFER**](ns-ntifs-ntfs_volume_data_buffer.md)

[**NTFS_EXTENDED_VOLUME_DATA**](ns-ntifs-ntfs_extended_volume_data.md)

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md)

[**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md)
