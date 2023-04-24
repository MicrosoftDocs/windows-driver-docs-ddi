---
UID: NI:ntifs.FSCTL_REARRANGE_FILE
tech.root: ifsk
title: FSCTL_REARRANGE_FILE
ms.date: 04/17/2023
targetos: Windows
description: Learn more about the FSCTL_REARRANGE_FILE FS control code.
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
req.target-min-winverclnt: Windows 10, version 1809
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
 - FSCTL_REARRANGE_FILE
f1_keywords:
 - FSCTL_REARRANGE_FILE
 - ntifs/FSCTL_REARRANGE_FILE
dev_langs:
 - c++
helpviewer_keywords:
 - FSCTL_REARRANGE_FILE
---

## -description

**FSCTL_REARRANGE_FILE** rearranges allocation within the file, moving clusters from a requested contiguous source range within a file to another location within the same file.

## -ioctlparameters

### -input-buffer

Pointer to a [**REARRANGE_FILE_DATA**](ns-ntifs-rearrange_file_data.md) structure that describes the allocation to be rearranged. (For 32-bit callers, the input buffer is a pointer to a **REARRANGE_FILE_DATA32** structure.)

### -input-buffer-length

Size in bytes of the input buffer.

### -output-buffer

None; set to NULL.

### -output-buffer-length

Set to zero.

### -in-out-buffer

### -inout-buffer-length

### -status-block

## Return values

**FSCTL_REARRANGE_FILE** returns STATUS_SUCCESS upon successful completion; otherwise it returns an NTSTATUS code such as one of the following.

| Return code | Meaning |
| ----------- | ------- |
| STATUS_ACCESS_DENIED    | Only kernel-mode calls are allowed. |
| STATUS_BUFFER_TOO_SMALL | The specified input buffer length is smaller than sizeof(REARRANGE_FILE_DATA). |
| STATUS_PENDING          | Operation completion is pending. |

## -remarks

[Request parameters](ns-ntifs-rearrange_file_data.md) contain source and target file byte offsets, and length in bytes of the source region to move, all of which must be cluster-aligned.

* If moving clusters down, the target file offset indicates the point at which the lower boundary of the moving source range should be aligned.
* If moving clusters up, the target file offset indicates the point at which the source range's upper boundary should be aligned.

In both cases, the target offset indicates that the source range should be inserted before the cluster that begins at the target offset, the distinction being forced by the constraint that the allocation size remains fixed.

Unlike [**FSCTL_SHUFFLE_FILE**](ni-ntifs-fsctl_shuffle_file.md), **FSCTL_REARRANGE_FILE** doesn't allow adding allocations containing random data.

To perform this operation, call [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md) with the following parameters.

| Parameter | Description |
| --------- | ----------- |
| **Instance** | [in] For **FltFsControlFile** only. An opaque instance pointer for the caller. This parameter is required and cannot be NULL. |
| **FileObject** | [in] For **FltFsControlFile** only. A file object pointer for the file or directory that is the target of this request. This parameter is required and cannot be NULL. |
| **FileHandle** | [in] For **ZwFsControlFile** only. File handle of the file or directory that is the target of this request. This parameter is required and cannot be NULL. |
| **IoStatusBlock** | [out] For **ZwFsControlFile** only. Pointer to an [**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md) structure that contains the final status of the request. |
| **FsControlCode** | [in] Set to **FSCTL_REARRANGE_FILE**. |
| **InputBuffer** | [in] See IOCTL parameters. |
| **InputBufferLength** | [in] See IOCTL parameters. |

## -see-also

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md)

[**FSCTL_SHUFFLE_FILE**](ni-ntifs-fsctl_shuffle_file.md)

[**REARRANGE_FILE_DATA**](ns-ntifs-rearrange_file_data.md)

[**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md)
