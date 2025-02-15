---
UID: NI:ntifs.FSCTL_READ_USN_JOURNAL
tech.root: ifsk
title: FSCTL_READ_USN_JOURNAL
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FSCTL_READ_USN_JOURNAL control code.
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
 - FSCTL_READ_USN_JOURNAL
f1_keywords:
 - FSCTL_READ_USN_JOURNAL
 - ntifs/FSCTL_READ_USN_JOURNAL
dev_langs:
 - c++
helpviewer_keywords:
 - FSCTL_READ_USN_JOURNAL
---

## -description

The **FSCTL_READ_USN_JOURNAL** control code retrieves the set of update sequence number (USN) change journal records between two specified USN values. See Remarks.

## -ioctlparameters

### -ioctl-major-code

FSCTL_READ_USN_JOURNAL

### -input-buffer

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

## -remarks

There are two control codes that return USN records, FSCTL_READ_USN_JOURNAL and FSCTL_ENUM_USN_DATA. Use the latter when you want a listing (enumeration) of the USN records between two USNs. Use the former when you want to select by USN.

To perform this operation, call [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md) with the following parameters.

* **FileObject** [in]: Parameter for [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) only. A file object pointer for the remote volume. This parameter is required and can't be NULL.

* **FileHandle** [in]: Parameter for [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md) only. A handle for the remote volume. This parameter is required and can't be NULL.

* **FsControlCode** [in]: A control code for the operation. Use **FSCTL_READ_USN_JOURNAL** for this operation.

* **InputBuffer** [in]: Pointer to a [**READ_USN_JOURNAL_DATA**](ns-ntifs-read_usn_journal_data_v0.md) structure.

* **InputBufferLength** [in]: Size in bytes of the buffer at **InputBuffer**.

* **OutputBuffer** [out]: Pointer to a [**USN_RECORD_V2**](ns-ntifs-usn_record_v2.md) structure that receives the USN records.

* **OutputBufferLength** [in]: Size in bytes of the buffer at **OutputBuffer**.

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md) returns STATUS_SUCCESS if the operation succeeds. Otherwise, the appropriate function returns the appropriate NTSTATUS error code.

## -see-also

[**READ_USN_JOURNAL_DATA_V0**](ns-ntifs-read_usn_journal_data_v0.md)

[**READ_USN_JOURNAL_DATA_V1**](ns-ntifs-read_usn_journal_data_v1.md)

[**USN_RECORD_V2**](ns-ntifs-usn_record_v2.md)

[**USN_RECORD_V3**](ns-ntifs-usn_record_v3.md)

[**USN_RECORD_V4**](ns-ntifs-usn_record_v4.md)
