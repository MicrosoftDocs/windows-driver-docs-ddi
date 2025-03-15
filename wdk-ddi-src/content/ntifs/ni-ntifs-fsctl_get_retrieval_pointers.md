---
UID: NI:ntifs.FSCTL_GET_RETRIEVAL_POINTERS
tech.root: ifsk
title: FSCTL_GET_RETRIEVAL_POINTERS
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FSCTL_GET_RETRIEVAL_POINTERS control code.
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
 - FSCTL_GET_RETRIEVAL_POINTERS
f1_keywords:
 - FSCTL_GET_RETRIEVAL_POINTERS
 - ntifs/FSCTL_GET_RETRIEVAL_POINTERS
dev_langs:
 - c++
helpviewer_keywords:
 - FSCTL_GET_RETRIEVAL_POINTERS
---

## -description

Given a file handle, the **FSCTL_GET_RETRIEVAL_POINTERS** control code retrieves a data structure that describes the allocation and location on disk of a specified file; or, given a volume handle, it retrieves the locations of bad clusters on the volume.

## -ioctlparameters

### -ioctl-major-code

FSCTL_GET_RETRIEVAL_POINTERS

### -input-buffer

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

## -remarks

To perform this operation, call [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md).

See [FSCTL_GET_RETRIEVAL_POINTERS IOCTL (winioctl.h)](/windows/win32/api/winioctl/ni-winioctl-fsctl_get_retrieval_pointers) for more information.

## -see-also

[RETRIEVAL_POINTERS_BUFFER structure (winioctl.h)](/windows/win32/api/winioctl/ns-winioctl-retrieval_pointers_buffer)
