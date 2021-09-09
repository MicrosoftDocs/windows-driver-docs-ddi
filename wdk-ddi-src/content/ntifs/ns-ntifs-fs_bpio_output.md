---
UID: NS:ntifs._FS_BPIO_OUTPUT
tech.root: ifsk
title: FS_BPIO_OUTPUT
ms.date: 07/08/2021
targetos: Windows
description: The FS_BPIO_OUTPUT structure is used to return information about the BypassIO operation for the FSCTL_MANAGE_BYPASS_IO control code.
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
req.typenames: FS_BPIO_OUTPUT, *PFS_BPIO_OUTPUT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FS_BPIO_OUTPUT
 - PFS_BPIO_OUTPUT
 - FS_BPIO_OUTPUT
f1_keywords:
 - _FS_BPIO_OUTPUT
 - ntifs/_FS_BPIO_OUTPUT
 - PFS_BPIO_OUTPUT
 - ntifs/PFS_BPIO_OUTPUT
 - FS_BPIO_OUTPUT
 - ntifs/FS_BPIO_OUTPUT
dev_langs:
 - c++
---

## -description

The **FS_BPIO_OUTPUT** structure is used to return information about the BypassIO operation for the [**FSCTL_MANAGE_BYPASS_IO**](ni-ntifs-fsctl_manage_bypass_io.md) control code.

## -struct-fields

### -field Operation

A [**FS_BPIO_OPERATIONS**](ne-ntifs-fs_bpio_operations.md) enum value that identifies the requested BypassIO operation. This field should be set to the same value passed in [**FS_BPIO_INPUT**](ns-ntifs-fs_bpio_input.md)**.Operation**.

### -field OutFlags

A [**FS_BPIO_OUTFLAGS**](ne-ntifs-fs_bpio_outflags.md) enum value that specifies the output flags for the operation.

### -field Reserved1

Reserved for system use. Set to zero.

### -field Reserved2

Reserved for system use. Set to zero.

### -field Enable

A [**FS_BPIO_RESULTS**](ns-ntifs-fs_bpio_results.md) structure in which to write the results when a [FS_BPIO_OP_ENABLE](ne-ntifs-fs_bpio_operations.md) operation was requested.

### -field Query

A [**FS_BPIO_RESULTS**](ns-ntifs-fs_bpio_results.md) structure in which to write the results when a [FS_BPIO_OP_QUERY](ne-ntifs-fs_bpio_operations.md) operation was requested.

### -field VolumeStackResume

A [**FS_BPIO_RESULTS**](ns-ntifs-fs_bpio_results.md) structure in which to write the results when a [FS_BPIO_OP_VOLUME_STACK_RESUME](ne-ntifs-fs_bpio_operations.md) operation was requested.

### -field StreamResume

A [**FS_BPIO_RESULTS**](ns-ntifs-fs_bpio_results.md) structure in which to write the results when a [FS_BPIO_OP_STREAM_RESUME](ne-ntifs-fs_bpio_operations.md) operation was requested.

### -field GetInfo

A [*FS_BPIO_INFO**](ns-ntifs-fs_bpio_info.md) structure in which to return information about the requested operation.

## -remarks

**FS_BPIO_OUTPUT** is a variable length structure.

See [BypassIO for filter drivers](/windows-hardware/drivers/ifs/bypassio) for more information.

## -see-also

[*FS_BPIO_INFO**](ns-ntifs-fs_bpio_info.md)

[**FS_BPIO_OPERATIONS**](ne-ntifs-fs_bpio_operations.md)

[**FS_BPIO_OUTFLAGS**](ne-ntifs-fs_bpio_outflags.md)

[**FS_BPIO_RESULTS**](ns-ntifs-fs_bpio_results.md)

[**FSCTL_MANAGE_BYPASS_IO**](ni-ntifs-fsctl_manage_bypass_io.md)
