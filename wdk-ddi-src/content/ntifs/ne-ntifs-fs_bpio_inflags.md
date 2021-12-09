---
UID: NE:ntifs._FS_BPIO_INFLAGS
tech.root: ifsk
title: FS_BPIO_INFLAGS
ms.date: 12/08/2021
targetos: Windows
description: FS_BPIO_INFLAGS defines the BypassIO input flags for the FSCTL_MANAGE_BYPASS_IO control code.
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
 - _FS_BPIO_INFLAGS
 - FS_BPIO_INFLAGS
f1_keywords:
 - _FS_BPIO_INFLAGS
 - ntifs/_FS_BPIO_INFLAGS
 - FS_BPIO_INFLAGS
 - ntifs/FS_BPIO_INFLAGS
dev_langs:
 - c++
---

## -description

**FS_BPIO_INFLAGS** defines the BypassIO input flags for the [**FSCTL_MANAGE_BYPASS_IO**](ni-ntifs-fsctl_manage_bypass_io.md) control code.

## -enum-fields

### -field FSBPIO_INFL_None

No input flag(s) are set.

### -field FSBPIO_INFL_SKIP_STORAGE_STACK_QUERY

This flag suppresses the file system from sending [**IOCTL_STORAGE_MANAGE_BYPASS_IO**](../ntddstor/ni-ntddstor-ioctl_storage_manage_bypass_io.md) to the storage stack, and returns results based only on the filter stack. It applies to [**FS_BPIO_OP_QUERY**](ne-ntifs-fs_bpio_operations.md) operations only, and has no effect on **FS_BPIO_OP_ENABLE** operations.

## -remarks

**FS_BPIO_INFLAGS** is passed as an [input parameter](ns-ntifs-fs_bpio_input.md) to [**FSCTL_MANAGE_BYPASS_IO**](ni-ntifs-fsctl_manage_bypass_io.md).

See [BypassIO for filter drivers](/windows-hardware/drivers/ifs/bypassio) and [Supporting BypassIO operations](/windows-hardware/drivers/ifs/bypassio-operations) for more information.

## -see-also

[**FS_BPIO_INPUT**](ns-ntifs-fs_bpio_input.md)

[**FSCTL_MANAGE_BYPASS_IO**](ni-ntifs-fsctl_manage_bypass_io.md)
