---
UID: NI:ntifs.FSCTL_QUERY_USN_JOURNAL
tech.root: ifsk
title: FSCTL_QUERY_USN_JOURNAL
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FSCTL_QUERY_USN_JOURNAL control code.
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
 - FSCTL_QUERY_USN_JOURNAL
f1_keywords:
 - FSCTL_QUERY_USN_JOURNAL
 - ntifs/FSCTL_QUERY_USN_JOURNAL
dev_langs:
 - c++
helpviewer_keywords:
 - FSCTL_QUERY_USN_JOURNAL
---

## -description

The **FSCTL_QUERY_USN_JOURNAL** control code queries for information on the current update sequence number (USN) change journal, its records, and its capacity. See Remarks.

## -ioctlparameters

### -ioctl-major-code

FSCTL_QUERY_USN_JOURNAL

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

* **FsControlCode** [in]: A control code for the operation. Use **FSCTL_QUERY_USN_JOURNAL** for this operation.

* **InputBuffer** [in]: Not used.

* **InputBufferLength** [in]: Not used.

* **OutputBuffer** [out]: Pointer to a **USN_JOURNAL_DATA** structure that receives the information about the change journal.

* **OutputBufferLength** [in]: Size in bytes of the buffer at **OutputBuffer**.

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md) returns STATUS_SUCCESS if the operation succeeds. Otherwise, the appropriate function returns the appropriate NTSTATUS error code.

## -see-also

[**USN_JOURNAL_DATA_V0**](ns-ntifs-usn_journal_data_v0.md)

[**USN_JOURNAL_DATA_V1**](ns-ntifs-usn_journal_data_v1.md)

[**USN_JOURNAL_DATA_V2**](ns-ntifs-usn_journal_data_v2.md)
