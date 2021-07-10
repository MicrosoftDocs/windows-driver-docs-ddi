---
UID: NS:ntddstor._BPIO_OUTPUT
tech.root: storage
title: BPIO_OUTPUT
ms.date: 07/08/2021
targetos: Windows
description: The BPIO_OUTPUT structure is used to return information about the BypassIO operation for the IOCTL_STORAGE_MANAGE_BYPASS_IO control code.
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
req.typenames: BPIO_OUTPUT, *PBPIO_OUTPUT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _BPIO_OUTPUT
 - PBPIO_OUTPUT
 - BPIO_OUTPUT
f1_keywords:
 - _BPIO_OUTPUT
 - ntddstor/_BPIO_OUTPUT
 - PBPIO_OUTPUT
 - ntddstor/PBPIO_OUTPUT
 - BPIO_OUTPUT
 - ntddstor/BPIO_OUTPUT
dev_langs:
 - c++
---

## -description

The BPIO_OUTPUT structure is used to return information about the BypassIO operation for the [**IOCTL_STORAGE_MANAGE_BYPASS_IO**](ni-ntddstor-ioctl_storage_manage_bypass_io.md) control code.

## -struct-fields

### -field Version

The version of this structure. Set to ```sizeof(BPIO_OUTPUT)```.

### -field Size

The size of this structure plus all of its variable-sized fields, in bytes.

### -field Operation

A [**BPIO_OPERATIONS**](ne-ntddstor-bpio_operations.md) enum value that identifies the requested BypassIO operation. This field should be set to the same value passed in [**BPIO_INPUT**](ns-ntddstor-bpio_input.md)**.Operation**.

### -field OutFlags

A [**BPIO_OUTFLAGS**](ne-ntddstor-bpio_outflags.md) enum value that specifies the output flags for the operation.

### -field Reserved2

Reserved for system use. Set to zero.

### -field Enable

A [**BPIO_RESULTS**](ns-ntddstor-bpio_results.md) structure in which to write the results when a [BPIO_OP_ENABLE](ne-ntddstor-bpio_operations.md) operation was requested.

### -field Query

A [**BPIO_RESULTS**](ns-ntddstor-bpio_results.md) structure in which to write the results when a [BPIO_OP_QUERY](ne-ntddstor-bpio_operations.md) operation was requested.

## -remarks

See [BypassIO for storage drivers](/windows-hardware/drivers/storage/stornvme-feature-support/bypassio) for more information.

## -see-also

[**BPIO_OPERATIONS**](ne-ntddstor-bpio_operations.md)

[**BPIO_OUTFLAGS**](ne-ntddstor-bpio_outflags.md)

[**BPIO_RESULTS**](ns-ntddstor-bpio_results.md)

[**IOCTL_STORAGE_MANAGE_BYPASS_IO**](ni-ntddstor-ioctl_storage_manage_bypass_io.md)
