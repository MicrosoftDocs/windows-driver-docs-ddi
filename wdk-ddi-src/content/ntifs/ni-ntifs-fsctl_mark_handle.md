---
UID: NI:ntifs.FSCTL_MARK_HANDLE
tech.root: ifsk
title: FSCTL_MARK_HANDLE
ms.date: 10/07/2022
targetos: Windows
description: The FSCTL_MARK_HANDLE control code marks a specified file or directory and its change journal record with information about changes to that file or directory.
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
 - FSCTL_MARK_HANDLE
f1_keywords:
 - FSCTL_MARK_HANDLE
 - ntifs/FSCTL_MARK_HANDLE
dev_langs:
 - c++
---

## -description

The **FSCTL_MARK_HANDLE** control code marks a specified file or directory and its change journal record with information about changes to that file or directory.

## -ioctlparameters

### -ioctl-major-code

FSCTL_MARK_HANDLE

### -input-buffer

Pointer to a [**MARK_HANDLE_INFO**](ns-ntifs-mark_handle_info.md) structure containing the information to use to mark a specified file or directory, and its update sequence number (USN) change journal record with data about changes.

### -input-buffer-length

Size of the [**MARK_HANDLE_INFO**](ns-ntifs-mark_handle_info.md) structure that **InputBuffer** points to, in bytes.

### -output-buffer

Set to NULL.

### -output-buffer-length

n/a (ignored)

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
| **FsControlCode** | [in] Set to **FSCTL_MARK_HANDLE**. |
| **InputBuffer** | [in] Pointer to a [**MARK_HANDLE_INFO**](ns-ntifs-mark_handle_info.md) structure containing the information to use to mark a specified file or directory, and its update sequence number (USN) change journal record with data about changes. |
| **InputBufferLength** | [in] Size of the buffer that **InputBuffer** points to, in bytes. |
| **OutputBuffer** | [out] Set to NULL for this FSCTL. |
| **OutputBufferLength** | [in] Ignored when **OutputBuffer** is NULL. |
| **LengthReturned** | [out] Set to NULL. |

## -see-also

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md)

[**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md)
