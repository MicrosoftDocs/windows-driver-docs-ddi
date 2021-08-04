---
UID: NE:ntifs._FS_BPIO_OUTFLAGS
tech.root: ifsk
title: FS_BPIO_OUTFLAGS
ms.date: 07/08/2021
targetos: Windows
description: FS_BPIO_OUTFLAGS defines the BypassIO output flags for the FSCTL_MANAGE_BYPASS_IO control code.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FS_BPIO_OUTFLAGS
 - FS_BPIO_OUTFLAGS
f1_keywords:
 - _FS_BPIO_OUTFLAGS
 - ntifs/_FS_BPIO_OUTFLAGS
 - FS_BPIO_OUTFLAGS
 - ntifs/FS_BPIO_OUTFLAGS
dev_langs:
 - c++
---

## -description

**FS_BPIO_OUTFLAGS** defines the BypassIO output flags for the [**FSCTL_MANAGE_BYPASS_IO**](ni-ntifs-fsctl_manage_bypass_io.md) control code.

## -enum-fields

### -field FSBPIO_OUTFL_None

No output flag(s) are set.

### -field FSBPIO_OUTFL_VOLUME_STACK_BYPASS_PAUSED

When set, indicates that ByPassIO has been temporarily paused for this volume per a **FS_BPIO_OP_VOLUME_STACK_PAUSE** operation request.

### -field FSBPIO_OUTFL_STREAM_BYPASS_PAUSED

When set, indicates that BypassIO has been temporarily paused for this stream per a **FS_BPIO_OP_STREAM_PAUSE** operation request.

### -field FSBPIO_OUTFL_FILTER_ATTACH_BLOCKED

When set, indicates that a minifilter has attached to this volume whose supported features state indicates that it does not support BypassIO. All BypassIO is blocked on this volume.

### -field FSBPIO_OUTFL_COMPATIBLE_STORAGE_DRIVER

When set, indicates that the storage driver for this volume is BypassIO-compatible. This flag is defined only for **FS_BPIO_OP_ENABLE**, **FS_BPIO_OP_QUERY**, and **FS_BPIO_OP_GET_INFO** operations.

## -remarks

See [BypassIO](/windows-hardware/drivers/ifs/bypass.io) for more information.

## -see-also

[**FS_BPIO_OUTPUT**](ns-ntifs-fs_bpio_output.md)

[**FSCTL_MANAGE_BYPASS_IO**](ni-ntifs-fsctl_manage_bypass_io.md)
