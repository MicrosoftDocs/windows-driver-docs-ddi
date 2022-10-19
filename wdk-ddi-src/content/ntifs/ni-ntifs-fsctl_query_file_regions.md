---
UID: NI:ntifs.FSCTL_QUERY_FILE_REGIONS
tech.root:ifsk
title: FSCTL_QUERY_FILE_REGIONS
ms.date: 10/18/2022
targetos: Windows
description: Learn more about the FSCTL_QUERY_FILE_REGIONS FS control code.
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
req.target-min-winverclnt: Windows 8
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
 - FSCTL_QUERY_FILE_REGIONS
f1_keywords:
 - FSCTL_QUERY_FILE_REGIONS
 - ntifs/FSCTL_QUERY_FILE_REGIONS
dev_langs:
 - c++
helpviewer_keywords:
 - FSCTL_QUERY_FILE_REGIONS
---

## -description

**FSCTL_QUERY_FILE_REGIONS** queries a list of file regions, based on a specified usage parameter, for the file associated with the handle on which this FSCTL was invoked. This message contains an optional [**FILE_REGION_INPUT**](ns-ntifs-file_region_input.md) data element. If no **FILE_REGION_INPUT** parameter is specified, information for the entire size of the file is returned.

## -remarks

To perform this operation, call [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md) with the following parameters.

| Parameter | Description |
| --------- | ----------- |
| **Instance** | [in] For **FltFsControlFile** only. An opaque instance pointer for the caller. This parameter is required and cannot be NULL. |
| **FileObject** | [in] For **FltFsControlFile** only. A file object pointer for the file or directory that is the target of this request. This parameter is required and cannot be NULL. |
| **FileHandle** | [in] For **ZwFsControlFile** only. File handle of the file or directory that is the target of this request. This parameter is required and cannot be NULL. |
| **IoStatusBlock** | [out] For **ZwFsControlFile** only. Pointer to an [**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md) structure in which the final status of the request is returned. |
| **FsControlCode** | [in] Set to **FSCTL_QUERY_FILE_REGIONS**. |
| **InputBuffer** | [in/optional] Pointer to a [**FILE_REGION_INPUT**](ns-ntifs-file_region_input.md) structure that indicates the file region(s) to query. |
|  **InputBufferLength** | [in] Size of the buffer that **InputBuffer** points to, in bytes. |
| **OutputBuffer** | [out] Pointer to a [**FILE_REGION_OUTPUT**](ns-ntifs-file_region_output.md) structure in which the results of the query are returned. |
| **OutputBufferLength** | [out] Size of the buffer that **OutputBuffer** points to, in bytes. |
| **LengthReturned** | [out] Pointer to a caller-allocated variable that receives the size in bytes of the information returned in the buffer at **OutputBuffer**. |

## Return values

**FSCTL_QUERY_FILE_REGIONS** returns STATUS_SUCCESS upon successful completion; otherwise it returns an error code. On successful completion, the caller should first verify that **IoStatus.Information** is greater than or equal to **LengthReturned** before accessing the information returned in **OutputBuffer**.

## -see-also

[**FILE_REGION_INPUT**](ns-ntifs-file_region_input.md)

[**FILE_REGION_OUTPUT**](ns-ntifs-file_region_output.md)

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md)

[**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md)
