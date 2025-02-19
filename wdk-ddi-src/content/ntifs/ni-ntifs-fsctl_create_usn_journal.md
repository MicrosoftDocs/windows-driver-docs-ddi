---
UID: NI:ntifs.FSCTL_CREATE_USN_JOURNAL
tech.root: ifsk
title: FSCTL_CREATE_USN_JOURNAL
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FSCTL_CREATE_USN_JOURNAL control code.
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
 - FSCTL_CREATE_USN_JOURNAL
f1_keywords:
 - FSCTL_CREATE_USN_JOURNAL
 - ntifs/FSCTL_CREATE_USN_JOURNAL
dev_langs:
 - c++
helpviewer_keywords:
 - FSCTL_CREATE_USN_JOURNAL
---

## -description

The **FSCTL_CREATE_USN_JOURNAL** control code creates an update sequence number (USN) change journal stream on a target volume, or modifies an existing change journal stream. See Remarks.

## -ioctlparameters

### -ioctl-major-code

FSCTL_CREATE_USN_JOURNAL

### -input-buffer

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

## -remarks

**FSCTL_CREATE_USN_JOURNAL** can be used to:

* Create a new change journal stream for a volume. After the creation of the stream, the NTFS file system maintains a change journal for that volume.

* Modify an existing change journal stream. If a change journal stream already exists, **FSCTL_CREATE_USN_JOURNAL** sets it to the characteristics provided in the [**CREATE_USN_JOURNAL_DATA**] structure. The change journal stream eventually gets larger or is trimmed to the new size limit that **CREATE_USN_JOURNAL_DATA** imposes.

To perform this operation, call [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md) with the following parameters.

* **FileObject** [in]: Parameter for [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) only. A file object pointer for the remote volume. This parameter is required and can't be NULL.

* **FileHandle** [in]: Parameter for [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md) only. A handle for the remote volume. This parameter is required and can't be NULL.

* **FsControlCode** [in]: A control code for the operation. Use **FSCTL_CREATE_USN_JOURNAL** for this operation.

* **InputBuffer** [in]: Pointer to a [**CREATE_USN_JOURNAL_DATA**](ns-ntifs-create_usn_journal_data.md) structure that contains the parameters for the operation.

* **InputBufferLength** [in]: The size, in bytes, of the input buffer.

* **OutputBuffer** [out]: Not used.

* **OutputBufferLength** [in]: Not used.

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md) returns STATUS_SUCCESS if the operation succeeds. Otherwise, the appropriate function returns the appropriate NTSTATUS error code.

## -see-also

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md)

[**FSCTL_DELETE_USN_JOURNAL**](ni-ntifs-fsctl_delete_usn_journal.md)

[**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md)
