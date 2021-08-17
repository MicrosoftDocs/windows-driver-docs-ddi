---
UID: NS:ntddstor._BPIO_INPUT
tech.root: storage
title: BPIO_INPUT
ms.date: 07/08/2021
targetos: Windows
description: The BPIO_INPUT structure specifies the requested BypassIO operation and flags for the IOCTL_STORAGE_MANAGE_BYPASS_IO control code.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddstor.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: 
req.target-type: 
req.typenames: BPIO_INPUT, *PBPIO_INPUT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _BPIO_INPUT
 - PBPIO_INPUT
 - BPIO_INPUT
f1_keywords:
 - _BPIO_INPUT
 - ntddstor/_BPIO_INPUT
 - PBPIO_INPUT
 - ntddstor/PBPIO_INPUT
 - BPIO_INPUT
 - ntddstor/BPIO_INPUT
dev_langs:
 - c++
---

## -description

The BPIO_INPUT structure specifies the requested BypassIO operation and flags for the [**IOCTL_STORAGE_MANAGE_BYPASS_IO**](ni-ntddstor-ioctl_storage_manage_bypass_io.md) control code.

## -struct-fields

### -field Version

The version of this structure. Set to ```sizeof(BPIO_INPUT)```.

### -field Size

The size of this structure plus all of its variable-sized fields, in bytes.

### -field Operation

A [**BPIO_OPERATIONS**](ne-ntddstor-bpio_operations.md) enum value that identifies the requested BypassIO operation.

### -field InFlags

A [**BPIO_INFLAGS**](ne-ntddstor-bpio_inflags.md) enum value that specifies the input flags for the operation.

### -field Reserved2

Reserved for system use. Must be set to zero.

## -remarks

See [BypassIO for storage drivers](/windows-hardware/drivers/storage/bypassio) for more information.

## -see-also

[**BPIO_INFLAGS**](ne-ntddstor-bpio_inflags.md)

[**BPIO_OPERATIONS**](ne-ntddstor-bpio_operations.md)

[**IOCTL_STORAGE_MANAGE_BYPASS_IO**](../ntddstor/ni-ntddstor-ioctl_storage_manage_bypass_io.md)
