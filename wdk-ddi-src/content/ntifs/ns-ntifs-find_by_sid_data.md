---
UID: NS:ntifs.FIND_BY_SID_DATA
tech.root: ifsk
title: FIND_BY_SID_DATA
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FIND_BY_SID_DATA structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: 
req.target-type: 
req.typenames: FIND_BY_SID_DATA, *PFIND_BY_SID_DATA
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FIND_BY_SID_DATA
 - PFIND_BY_SID_DATA
f1_keywords:
 - FIND_BY_SID_DATA
 - ntifs/FIND_BY_SID_DATA
 - PFIND_BY_SID_DATA
 - ntifs/PFIND_BY_SID_DATA
dev_langs:
 - c++
helpviewer_keywords:
 - FIND_BY_SID_DATA
---

## -description

The **FIND_BY_SID_DATA** structure contains data for the [**FSCTL_FIND_FILES_BY_SID**](ni-ntifs-fsctl_find_files_by_sid.md) control code.

## -struct-fields

### -field Restart

Indicates whether to restart the search. This member should be 1 on first call, so the search will start from the root. For subsequent calls, this member should be zero so the search will resume at the point where it stopped.

### -field Sid

A [**SID**](/windows/win32/api/winnt/ns-winnt-sid) structure that specifies the desired creator owner.

## -remarks

To perform this operation, call [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md).

See [FSCTL_FIND_FILES_BY_SID IOCTL (winioctl.h)](/windows/win32/api/winioctl/ni-winioctl-fsctl_find_files_by_sid).

## -see-also

[**FSCTL_FIND_FILES_BY_SID**](ni-ntifs-fsctl_find_files_by_sid.md)
