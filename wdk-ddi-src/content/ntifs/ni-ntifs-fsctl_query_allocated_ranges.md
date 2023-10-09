---
UID: NI:ntifs.FSCTL_QUERY_ALLOCATED_RANGES
tech.root: ifsk
title: FSCTL_QUERY_ALLOCATED_RANGES
ms.date: 10/07/2022
targetos: Windows
description: Learn more about the FSCTL_QUERY_ALLOCATED_RANGES FSCTL.
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
req.target-min-winverclnt: Windows 2000
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
 - FSCTL_QUERY_ALLOCATED_RANGES
f1_keywords:
 - FSCTL_QUERY_ALLOCATED_RANGES
 - ntifs/FSCTL_QUERY_ALLOCATED_RANGES
dev_langs:
 - c++
helpviewer_keywords:
 - FSCTL_QUERY_ALLOCATED_RANGES
ms.custom: engagement-fy23
---

## -description

**FSCTL_QUERY_ALLOCATED_RANGES** requests a scan of a file or alternate [stream](/openspecs/windows_protocols/ms-fscc/8ac44452-328c-4d7b-a784-d72afd19bd9f#gt_f3529cd8-50da-4f36-aa0b-66af455edbb6) looking for byte ranges that can contain nonzero data, and then return of information on those ranges. Only sparse files can have zeroed ranges known to the operating system. For other files, the output buffer will contain only a single range that contains the starting point and the length requested.

## -ioctlparameters

### -ioctl-major-code

FSCTL_QUERY_ALLOCATED_RANGES

### -input-buffer

Pointer to a [**FILE_ALLOCATED_RANGE_BUFFER**](ns-ntifs-file_allocated_range_buffer.md) structure that indicates the range to query for allocation.

### -input-buffer-length

Size of the [**FILE_ALLOCATED_RANGE_BUFFER**](ns-ntifs-file_allocated_range_buffer.md) structure that **InputBuffer** points to, in bytes.

### -output-buffer

Pointer to an array of zero or more [**FILE_ALLOCATED_RANGE_BUFFER**](ns-ntifs-file_allocated_range_buffer.md) data elements in which the results of the query are returned. See below for more information.

### -output-buffer-length

Size of the buffer that **OutputBuffer** points to, in bytes.

### -in-out-buffer

n/a

### -inout-buffer-length

n/a

### -status-block

Reserved for system use.

## -remarks

To perform this operation, call [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md) with the following parameters.

| Parameter | Description |
| --------- | ----------- |
| **Instance** | [in] For **FltFsControlFile** only. An opaque instance pointer for the caller. This parameter is required and cannot be NULL. |
| **FileObject** | [in] For **FltFsControlFile** only. A file object pointer for the file or directory that is the target of this request. This parameter is required and cannot be NULL. |
| **FileHandle** | [in] For **ZwFsControlFile** only. File handle of the file or directory that is the target of this request. This parameter is required and cannot be NULL. |
| **IoStatusBlock** | [out] For **ZwFsControlFile** only. Pointer to an [**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md) structure that contains the final status of the request. |
| **FsControlCode** | [in] Set to **FSCTL_QUERY_ALLOCATED_RANGES**. |
| **InputBuffer** | [in] Pointer to a [**FILE_ALLOCATED_RANGE_BUFFER**](ns-ntifs-file_allocated_range_buffer.md) structure that indicates the range to query for allocation. |
| **InputBufferLength** | [in] Size of the buffer that **InputBuffer** points to, in bytes. |
| **OutputBuffer** | [out] Pointer to an array of zero or more [**FILE_ALLOCATED_RANGE_BUFFER**](ns-ntifs-file_allocated_range_buffer.md) data elements in which the results of the query are returned. See below for more information. |
| **OutputBufferLength** | [out] Size of the buffer that **OutputBuffer** points to, in bytes. |
| **LengthReturned** | [out] Pointer to a caller-allocated variable that receives the size in bytes of the information returned in the buffer at **OutputBuffer**. |

**FSCTL_QUERY_ALLOCATED_RANGES** returns an array of zero or more [**FILE_ALLOCATED_RANGE_BUFFER**](ns-ntifs-file_allocated_range_buffer.md) data elements in the buffer that **OutputBuffer** points to. The number of **FILE_ALLOCATED_RANGE_BUFFER** elements returned is computed by dividing the value returned in **LengthReturned** by ```sizeof(FILE_ALLOCATED_RANGE_BUFFER)```. The returned ranges must intersect the range specified in **InputBuffer**. Zero **FILE_ALLOCATED_RANGE_BUFFER** data elements are returned when the file has no allocated ranges.

## Return values

**FSCTL_QUERY_ALLOCATED_RANGES** returns STATUS_SUCCESS upon successful completion; otherwise it returns an error code. Common error codes follow.

| Error code | Meaning |
| ---------- | ------- |
| STATUS_INVALID_PARAMETER | A parameter is invalid. For example: the handle is not to a file; the size of **InputBuffer** is less than the size of a **FILE_ALLOCATED_RANGE_BUFFER** structure;  **FileOffset** is less than zero; **Length** is less than zero; or **FileOffset** plus **Length** is larger than 0x7FFFFFFFFFFFFFFF. |
| STATUS_INVALID_USER_BUFFER | The input buffer or output buffer is not aligned to a 4-byte boundary. |
| STATUS_BUFFER_TOO_SMALL | The output buffer is too small to contain a **FILE_ALLOCATED_RANGE_BUFFER** structure. |
| STATUS_BUFFER_OVERFLOW | The output buffer is too small to contain the required number of **FILE_ALLOCATED_RANGE_BUFFER** structures. |

## -see-also

[**FILE_ALLOCATED_RANGE_BUFFER**](ns-ntifs-file_allocated_range_buffer.md)

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md)

[**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md)
