---
UID: NI:ntifs.FSCTL_ENUM_USN_DATA
tech.root: ifsk
title: FSCTL_ENUM_USN_DATA
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FSCTL_ENUM_USN_DATA control code.
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
 - FSCTL_ENUM_USN_DATA
f1_keywords:
 - FSCTL_ENUM_USN_DATA
 - ntifs/FSCTL_ENUM_USN_DATA
dev_langs:
 - c++
helpviewer_keywords:
 - FSCTL_ENUM_USN_DATA
---

## -description

The **FSCTL_ENUM_USN_DATA** control code enumerates the update sequence number (USN) data between two specified boundaries to get master file table (MFT) records.

## -ioctlparameters

### -ioctl-major-code

FSCTL_ENUM_USN_DATA

### -input-buffer

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

## -remarks

To perform this operation, call [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md).

See [FSCTL_ENUM_USN_DATA IOCTL (winioctl.h)](/windows/win32/api/winioctl/ni-winioctl-fsctl_enum_usn_data) for more information.

## -see-also

[**MFT_ENUM_DATA**](ns-ntifs-mft_enum_data_v0.md)

[**USN_RECORD**](ns-ntifs-usn_record_v2.md)

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md)

[**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md)
