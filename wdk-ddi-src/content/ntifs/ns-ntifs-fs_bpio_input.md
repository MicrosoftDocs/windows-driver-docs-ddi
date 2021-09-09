---
UID: NS:ntifs._FS_BPIO_INPUT
tech.root: ifsk
title: FS_BPIO_INPUT
ms.date: 07/08/2021
targetos: Windows
description: The FS_BPIO_INPUT structure specifies the requested BypassIO operation and flags for the FSCTL_MANAGE_BYPASS_IO control code.
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
req.typenames: FS_BPIO_INPUT, *PFS_BPIO_INPUT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FS_BPIO_INPUT
 - PFS_BPIO_INPUT
 - FS_BPIO_INPUT
f1_keywords:
 - _FS_BPIO_INPUT
 - ntifs/_FS_BPIO_INPUT
 - PFS_BPIO_INPUT
 - ntifs/PFS_BPIO_INPUT
 - FS_BPIO_INPUT
 - ntifs/FS_BPIO_INPUT
dev_langs:
 - c++
---

## -description

The **FS_BPIO_INPUT** structure specifies the requested BypassIO operation and flags for the [**FSCTL_MANAGE_BYPASS_IO**](ni-ntifs-fsctl_manage_bypass_io.md) control code.

## -struct-fields

### -field Operation

A [**FS_BPIO_OPERATIONS**](ne-ntifs-fs_bpio_operations.md) enum value that identifies the requested BypassIO operation.

### -field InFlags

A [**FS_BPIO_INFLAGS**](ne-ntifs-fs_bpio_inflags.md) enum value that specifies the input flags for the operation.

### -field Reserved1

Reserved for system use. Must be set to zero.

### -field Reserved2

Reserved for system use. Must be set to zero.

## -remarks

See [BypassIO for filter drivers](/windows-hardware/drivers/ifs/bypassio) for more information.

## -see-also

[**FS_BPIO_INFLAGS**](ne-ntifs-fs_bpio_inflags.md)

[**FS_BPIO_OPERATIONS**](ne-ntifs-fs_bpio_operations.md)

[**FSCTL_MANAGE_BYPASS_IO**](ni-ntifs-fsctl_manage_bypass_io.md)
