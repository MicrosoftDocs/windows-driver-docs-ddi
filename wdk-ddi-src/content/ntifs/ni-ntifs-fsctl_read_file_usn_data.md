---
UID: NI:ntifs.FSCTL_READ_FILE_USN_DATA
tech.root: ifsk
title: FSCTL_READ_FILE_USN_DATA
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FSCTL_READ_FILE_USN_DATA control code.
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
 - FSCTL_READ_FILE_USN_DATA
f1_keywords:
 - FSCTL_READ_FILE_USN_DATA
 - ntifs/FSCTL_READ_FILE_USN_DATA
dev_langs:
 - c++
helpviewer_keywords:
 - FSCTL_READ_FILE_USN_DATA
---

## -description

The **FSCTL_READ_FILE_USN_DATA** control code retrieves the update sequence number (USN) change-journal information for the specified file or directory.

## -ioctlparameters

### -ioctl-major-code

FSCTL_READ_FILE_USN_DATA

### -input-buffer

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

## -remarks

To perform this operation, call [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md) with the following parameters.

* **FileObject** [in]: Parameter for [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) only. A file object pointer for the remote volume. This parameter is required and can't be NULL.

* **FileHandle** [in]: Parameter for [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md) only. A handle for the remote volume. This parameter is required and can't be NULL.

* **FsControlCode** [in]: A control code for the operation. Use **FSCTL_READ_USN_JOURNAL** for this operation.

* **InputBuffer** [in]: Pointer to a [**READ_FILE_USN_DATA**](ns-ntifs-read_file_usn_data.md) structure.

* **InputBufferLength** [in]: Size in bytes of the buffer at **InputBuffer**.

* **OutputBuffer** [out]: Pointer to a [**USN_RECORD**](ns-ntifs-usn_record_v4.md) structure that receives the USN records.

* **OutputBufferLength** [in]: Size in bytes of the buffer at **OutputBuffer**.

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md) returns STATUS_SUCCESS if the operation succeeds. Otherwise, the appropriate function returns the appropriate NTSTATUS error code.

## -see-also

[**READ_FILE_USN_DATA**](ns-ntifs-read_file_usn_data.md)

[**USN_RECORD_V2**](ns-ntifs-usn_record_v2.md)

[**USN_RECORD_V3**](ns-ntifs-usn_record_v3.md)

[**USN_RECORD_V4**](ns-ntifs-usn_record_v4.md)
