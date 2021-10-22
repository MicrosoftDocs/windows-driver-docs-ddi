---
UID: NI:ntifs.FSCTL_MANAGE_BYPASS_IO
tech.root: ifsk
title: FSCTL_MANAGE_BYPASS_IO
ms.date: 07/08/2021
targetos: Windows
description: The FSCTL_MANAGE_BYPASS_IO control code controls BypassIO operations on a given file in the filter and file system stacks.
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
req.target-min-winverclnt: Windows 11
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
 - FSCTL_MANAGE_BYPASS_IO
f1_keywords:
 - FSCTL_MANAGE_BYPASS_IO
 - ntifs/FSCTL_MANAGE_BYPASS_IO
dev_langs:
 - c++
---

## -description

The **FSCTL_MANAGE_BYPASS_IO** control code controls BypassIO operations on a given file in the filter and file system stacks.

## -remarks

To perform this operation, call [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](/previous-versions/ff566462(v=vs.85)) with the following parameters.

| Parameter | Description |
| --------- | ----------- |
| **Instance** | [in] For **FltFsControlFile** only. An opaque instance pointer for the caller. This parameter is required and cannot be NULL. |
| **FileObject** | [in] For **FltFsControlFile** only. A file object pointer for the file or directory that is the target of this BypassIO operation request. This parameter is required and cannot be NULL. |
| **FileHandle** | [in] For **ZwFsControlFile** only. File handle of the file on which the BypassIO operation is being requested. This parameter is required and cannot be NULL. |
| **FsControlCode** | [in] Set to **FSCTL_MANAGE_BYPASS_IO**. |
| **InputBuffer** | [in] Pointer to a [**FS_BPIO_INPUT**](ns-ntifs-fs_bpio_input.md) structure containing information about the BypassIO request. |
| **InputBufferLength** | [in] Size of the buffer that **InputBuffer** points to, in bytes. |
| **OutputBuffer** | [out] Pointer to a [**FS_BPIO_OUTPUT**](ns-ntifs-fs_bpio_output.md) structure in which to return information about the BypassIO operation. |
| **OutputBufferLength** | [out] Size of the buffer that **OutputBuffer** points to, in bytes. |

See [BypassIO for filter drivers](/windows-hardware/drivers/ifs/bypassio) for more information.

## -see-also

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md)

[**FS_BPIO_INPUT**](ns-ntifs-fs_bpio_input.md)

[**FS_BPIO_OUTPUT**](ns-ntifs-fs_bpio_output.md)

[**ZwFsControlFile**](/previous-versions/ff566462(v=vs.85))