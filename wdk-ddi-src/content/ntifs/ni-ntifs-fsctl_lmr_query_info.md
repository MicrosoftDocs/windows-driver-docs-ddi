---
UID: NI:ntifs.FSCTL_LMR_QUERY_INFO
tech.root: ifsk
title: FSCTL_LMR_QUERY_INFO
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FSCTL_LMR_QUERY_INFO control code.
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
req.target-min-winverclnt: Windows 10 version 1809, and Windows 10 version 2004 and above versions
req.target-min-winversvr:  Windows Server 2019
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
 - FSCTL_LMR_QUERY_INFO
f1_keywords:
 - FSCTL_LMR_QUERY_INFO
 - ntifs/FSCTL_LMR_QUERY_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - FSCTL_LMR_QUERY_INFO
---

## -description

The **FSCTL_LMR_QUERY_INFO** control code retrieves the desired information for a remote file or directory opened locally.

## -ioctlparameters

### -ioctl-major-code

FSCTL_LMR_QUERY_INFO

### -input-buffer

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

## -remarks

To perform this operation, call [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md) with the following parameters.

- **FileObject** [in]: Parameter for [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) only. A file object pointer for the remote volume. This parameter is required and can't be NULL.

- **FileHandle** [in]: Parameter for [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md) only. A handle for the remote volume. This parameter is required and can't be NULL.

- **FsControlCode** [in]: A control code for the operation. Use **FSCTL_LMR_QUERY_INFO** for this operation.

- **InputBuffer** [in]: Pointer to a [**LMR_QUERY_INFO_PARAM**](ns-ntifs-lmr_query_info_param.md) structure that contains the type of information to be queried.

- **InputBufferLength** [in]: The size, in bytes, of the buffer pointed to by **InputBuffer**. This value is ```sizeof(LMR_QUERY_INFO_PARAM)```.

- **OutputBuffer** [out]: A pointer to a buffer that receives the desired information about the file or directory. The structure of the information returned in the output buffer is defined by the **Operation** specified in **InputBuffer**'s [**LMR_QUERY_INFO_PARAM**](ns-ntifs-lmr_query_info_param.md) structure.

- **OutputBufferLength** [out]: The size, in bytes, of the buffer pointed to by **OutputBuffer**.

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md) returns STATUS_SUCCESS if the operation succeeds. Otherwise, the appropriate function returns the appropriate NTSTATUS error code.

## -see-also

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md)

[**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md)
