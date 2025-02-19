---
UID: NI:ntifs.FSCTL_DELETE_USN_JOURNAL
tech.root: ifsk
title: FSCTL_DELETE_USN_JOURNAL
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FSCTL_DELETE_USN_JOURNAL control code.
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
 - FSCTL_DELETE_USN_JOURNAL
f1_keywords:
 - FSCTL_DELETE_USN_JOURNAL
 - ntifs/FSCTL_DELETE_USN_JOURNAL
dev_langs:
 - c++
helpviewer_keywords:
 - FSCTL_DELETE_USN_JOURNAL
---

## -description

The **FSCTL_DELETE_USN_JOURNAL** control code deletes the update sequence number (USN) change journal on a volume, or waits for notification of change journal deletion. See Remarks.

## -ioctlparameters

### -ioctl-major-code

FSCTL_DELETE_USN_JOURNAL

### -input-buffer

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

## -remarks

**FSCTL_DELETE_USN_JOURNAL** can be used to:

* Delete a change journal. The NTFS file system starts a deletion operation and returns immediately to the calling process, unless the **USN_DELETE_FLAG_NOTIFY** flag is set in the **DeleteFlags** member of [**DELETE_USN_JOURNAL_DATA**](ns-ntifs-delete_usn_journal_data.md).

  If the **USN_DELETE_FLAG_NOTIFY** and **USN_DELETE_FLAG_DELETE** flags are both set, a call to **FSCTL_DELETE_USN_JOURNAL** begins the deletion process. Then the call either blocks the calling thread and waits for the deletion (on a synchronous or non-overlapped call), or sets up event notification by using an I/O completion port or other mechanism, and returns (on an asynchronous or overlapped call).

* Receive notification that a change journal deletion is complete, by setting only **USN_DELETE_FLAG_NOTIFY**. If you do so, the **FSCTL_DELETE_USN_JOURNAL** operation either waits until the deletion completes before returning (on a synchronous or non-overlapped call), or sets up event notification by using an I/O completion port or other mechanism (on an asynchronous or overlapped call).

To perform this operation, call [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md) with the following parameters.

* **FileObject** [in]: Parameter for [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) only. A file object pointer for the remote volume. This parameter is required and can't be NULL.

* **FileHandle** [in]: Parameter for [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md) only. A handle for the remote volume. This parameter is required and can't be NULL.

* **FsControlCode** [in]: A control code for the operation. Use **FSCTL_CREATE_USN_JOURNAL** for this operation.

* **InputBuffer** [in]: Pointer to a [**DELETE_USN_JOURNAL_DATA**](ns-ntifs-delete_usn_journal_data.md) structure that contains the parameters for the operation.

* **InputBufferLength** [in]: The size, in bytes, of the input buffer.

* **OutputBuffer** [out]: Not used.

* **OutputBufferLength** [in]: Not used.

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md) returns STATUS_SUCCESS if the operation succeeds. Otherwise, the appropriate function returns the appropriate NTSTATUS error code.

## -see-also

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md)

[**FSCTL_CREATE_USN_JOURNAL**](ni-ntifs-fsctl_create_usn_journal.md)

[**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md)
