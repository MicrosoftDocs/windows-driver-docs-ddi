---
UID: NE:ntifs._FS_BPIO_OPERATIONS
tech.root: ifsk
title: FS_BPIO_OPERATIONS
ms.date: 12/08/2021
targetos: Windows
description: FS_BPIO_OPERATIONS defines the various BypassIO operations supported by the FSCTL_MANAGE_BYPASS_IO control code.
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
 - _FS_BPIO_OPERATIONS
 - FS_BPIO_OPERATIONS
f1_keywords:
 - _FS_BPIO_OPERATIONS
 - ntifs/_FS_BPIO_OPERATIONS
 - FS_BPIO_OPERATIONS
 - ntifs/FS_BPIO_OPERATIONS
dev_langs:
 - c++
---

## -description

**FS_BPIO_OPERATIONS** defines the various BypassIO operations supported by the [**FSCTL_MANAGE_BYPASS_IO**](ni-ntifs-fsctl_manage_bypass_io.md) control code.

## -enum-fields

### -field FS_BPIO_OP_ENABLE:1

Requests that BypassIO be enabled for the given file, which means a driver might not see all non-cached reads for that file.

### -field FS_BPIO_OP_DISABLE:2

Informs filters and file systems that BypassIO is being disabled on the specified file.

### -field FS_BPIO_OP_QUERY:3

Queries whether BypassIO can be enabled for the given file.

### -field FS_BPIO_OP_VOLUME_STACK_PAUSE:4

Requests that BypassIO be paused on the specified volume/storage stack.

### -field FS_BPIO_OP_VOLUME_STACK_RESUME:5

Requests that BypassIO processing be resumed on the given volume.

### -field FS_BPIO_OP_STREAM_PAUSE:6

Requests that BypassIO processing be paused on a stream.

### -field FS_BPIO_OP_STREAM_RESUME:7

Requests that BypassIO processing be resumed on a stream.

### -field FS_BPIO_OP_GET_INFO:8

Requests information about the BypassIO state of the volume.

### -field FS_BPIO_OP_MAX_OPERATION

Valid BypassIO operation values are less than this value.

## -remarks

See [BypassIO for filter drivers](/windows-hardware/drivers/ifs/bypassio) and [Supporting BypassIO operations](/windows-hardware/drivers/ifs/bypassio-operations) for more information.

## -see-also

[**FSCTL_MANAGE_BYPASS_IO**](ni-ntifs-fsctl_manage_bypass_io.md)
