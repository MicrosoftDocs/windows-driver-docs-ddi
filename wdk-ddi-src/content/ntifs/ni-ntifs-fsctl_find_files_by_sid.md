---
UID: NI:ntifs.FSCTL_FIND_FILES_BY_SID
tech.root: ifsk
title: FSCTL_FIND_FILES_BY_SID
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FSCTL_FIND_FILES_BY_SID control code.
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
 - FSCTL_FIND_FILES_BY_SID
f1_keywords:
 - FSCTL_FIND_FILES_BY_SID
 - ntifs/FSCTL_FIND_FILES_BY_SID
dev_langs:
 - c++
helpviewer_keywords:
 - FSCTL_FIND_FILES_BY_SID
---

## -description

The **FSCTL_FIND_FILES_BY_SID** control code searches a directory for a file whose creator owner matches the specified security identifier (SID).

## -ioctlparameters

### -ioctl-major-code

FSCTL_FIND_FILES_BY_SID

### -input-buffer

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

## -remarks

To perform this operation, call [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md).

See [FSCTL_FIND_FILES_BY_SID IOCTL (winioctl.h)](/windows/win32/api/winioctl/ni-winioctl-fsctl_find_files_by_sid).

## -see-also

[**FIND_BY_SID_DATA**](ns-ntifs-find_by_sid_data.md)

[**FIND_BY_SID_OUTPUT**](ns-ntifs-find_by_sid_output.md)

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md)

[**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md)
