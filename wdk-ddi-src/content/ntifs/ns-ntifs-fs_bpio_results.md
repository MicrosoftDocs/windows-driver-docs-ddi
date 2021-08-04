---
UID: NS:ntifs._FS_BPIO_RESULTS
tech.root: ifsk
title: FS_BPIO_RESULTS
ms.date: 07/08/2021
targetos: Windows
description: The FS_BPIO_RESULTS structure defines BypassIO operation-specific outputs for FS_BPIO_OP_ENABLE and FS_BPIO_OP_QUERY operations when a driver is failing the operation.
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
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: 
req.target-type: 
req.typenames: FS_BPIO_RESULTS, *PFS_BPIO_RESULTS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FS_BPIO_RESULTS
 - PFS_BPIO_RESULTS
 - FS_BPIO_RESULTS
f1_keywords:
 - _FS_BPIO_RESULTS
 - ntifs/_FS_BPIO_RESULTS
 - PFS_BPIO_RESULTS
 - ntifs/PFS_BPIO_RESULTS
 - FS_BPIO_RESULTS
 - ntifs/FS_BPIO_RESULTS
dev_langs:
 - c++
---

## -description

The **FS_BPIO_RESULTS** structure defines BypassIO operation-specific outputs for [**FS_BPIO_OP_ENABLE** and **FS_BPIO_OP_QUERY** operations](ne-ntifs-fs_bpio_operations.md) when a driver is failing the operation.

## -struct-fields

### -field OpStatus

Receives a NTSTATUS code available to the caller that identifies why the failing driver cannot support BypassIO for this file. This field should only be set by the first driver to fail the enable/query request.

### -field FailingDriverNameLen

Receives the length of the string stored in **FailingDriverName**, in characters.

### -field FailingDriverName

Receives a string that specifies the name of the driver that failed the request. For diagnostic reasons, a driver must store its name when it fails a [**FS_BPIO_OP_ENABLE** or **FS_BPIO_OP_QUERY** operation](ne-ntifs-fs_bpio_operations.md). The name must match the actual name of the driver that is used by the system; for example, *ntfs.sys*. This string is not guaranteed to be NULL-terminated.

### -field FailureReasonLen

Receives the length of the string stored in **FailingReason**, in characters.

### -field FailureReason

Receives a unique, descriptive string describing why the driver vetoed the enable/query request. This string is used for diagnostic reasons, and should be in English so that it does not need to be localized. This string is not guaranteed to be NULL-terminated.

## -remarks

**FS_BPIO_RESULTS** is returned in the [**FS_BPIO_OPERATIONS**](ne-ntifs-fs_bpio_operations.md) structure when a driver fails an enable or query BypassIO operation.

See [BypassIO](/windows-hardware/drivers/ifs/bypass.io) for more information.

## -see-also

[**FS_BPIO_OPERATIONS**](ne-ntifs-fs_bpio_operations.md)

[**FSCTL_MANAGE_BYPASS_IO**](ni-ntifs-fsctl_manage_bypass_io.md)
