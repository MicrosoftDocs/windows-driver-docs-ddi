---
UID: NS:ntifs._FS_BPIO_INFO
tech.root: ifsk
title: FS_BPIO_INFO
ms.date: 12/08/2021
targetos: Windows
description: The FS_BPIO_INFO structure provides information about the BypassIO state of the volume.
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
req.typenames: FS_BPIO_INFO, *PFS_BPIO_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FS_BPIO_INFO
 - PFS_BPIO_INFO
 - FS_BPIO_INFO
f1_keywords:
 - _FS_BPIO_INFO
 - ntifs/_FS_BPIO_INFO
 - PFS_BPIO_INFO
 - ntifs/PFS_BPIO_INFO
 - FS_BPIO_INFO
 - ntifs/FS_BPIO_INFO
dev_langs:
 - c++
---

## -description

The **FS_BPIO_INFO** structure provides information about the BypassIO state of the volume.

## -struct-fields

### -field ActiveBypassIoCount

The number of BypassIO-enabled files that are currently open.

### -field StorageDriverNameLen

Receives the length of the string stored in **StorageDriverName**, in characters.

### -field StorageDriverName

Receives a string that specifies the name of the storage driver for this volume.

## -remarks

**FS_BPIO_INFO** is returned when the requested BypassIO operation is **FS_BPIO_OP_GET_INFO**, and in the [**FS_BPIO_OPERATIONS**](ne-ntifs-fs_bpio_operations.md) structure when the requested BypassIO operation is **FS_BPIO_OP_ENABLE** or **FS_BPIO_OP_QUERY**.

See [BypassIO for filter drivers](/windows-hardware/drivers/ifs/bypassio) and [Supporting BypassIO operations](/windows-hardware/drivers/ifs/bypassio-operations) for more information.

## -see-also

[**FS_BPIO_OPERATIONS**](ne-ntifs-fs_bpio_operations.md)

[**FS_BPIO_OUTPUT**](ns-ntifs-fs_bpio_output.md)

[**FSCTL_MANAGE_BYPASS_IO**](ni-ntifs-fsctl_manage_bypass_io.md)
