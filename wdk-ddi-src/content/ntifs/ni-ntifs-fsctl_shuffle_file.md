---
UID: NI:ntifs.FSCTL_SHUFFLE_FILE
tech.root: ifsk
title: FSCTL_SHUFFLE_FILE
ms.date: 04/17/2023
targetos: Windows
description: Learn more about the FSCTL_SHUFFLE_FILE FS control code.
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
 - FSCTL_SHUFFLE_FILE
f1_keywords:
 - FSCTL_SHUFFLE_FILE
 - ntifs/FSCTL_SHUFFLE_FILE
dev_langs:
 - c++
helpviewer_keywords:
 - FSCTL_SHUFFLE_FILE
---

## -description

**FSCTL_SHUFFLE_FILE** adds or removes allocation from within the specified file.

## -ioctlparameters

### -input-buffer

Pointer to a [**SHUFFLE_FILE_DATA**](ns-ntifs-shuffle_file_data.md) structure that describes the allocation to be shuffled.

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

**FSCTL_SHUFFLE_FILE** returns STATUS_SUCCESS upon successful completion; otherwise it returns an NTSTATUS code such as one of the following.

| Return code | Meaning |
| ----------- | ------- |
| STATUS_ACCESS_DENIED         | For various reasons, including only kernel-mode calls are allowed, or the volume is locked. |
| STATUS_BUFFER_TOO_SMALL      | The specified input buffer length is smaller than sizeof(SHUFFLE_FILE_DATA). |
| STATUS_MEDIA_WRITE_PROTECTED | Shuffling is not allowed on a read-only volume. |

## -remarks

This control code will cause data to shift within the file. The caller is responsible for protecting/erasing the random data within the added allocation.

To perform this operation, call [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md) with the following parameters.

| Parameter | Description |
| --------- | ----------- |
| **Instance** | [in] For **FltFsControlFile** only. An opaque instance pointer for the caller. This parameter is required and cannot be NULL. |
| **FileObject** | [in] For **FltFsControlFile** only. A file object pointer for the file or directory that is the target of this request. This parameter is required and cannot be NULL. |
| **FileHandle** | [in] For **ZwFsControlFile** only. File handle of the file or directory that is the target of this request. This parameter is required and cannot be NULL. |
| **IoStatusBlock** | [out] For **ZwFsControlFile** only. Pointer to an [**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md) structure that contains the final status of the request. |
| **FsControlCode** | [in] Set to **FSCTL_SHUFFLE_FILE**. |
| **InputBuffer** | [in] See IOCTL parameters. |
| **InputBufferLength** | [in] See IOCTL parameters. |

## -see-also

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md)

[**FSCTL_REARRANGE_FILE**](ni-ntifs-fsctl_rearrange_file.md)

[**SHUFFLE_FILE_DATA**](ns-ntifs-shuffle_file_data.md)

[**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md)
