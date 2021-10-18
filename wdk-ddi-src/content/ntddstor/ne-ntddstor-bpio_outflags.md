---
UID: NE:ntddstor._BPIO_OUTFLAGS
tech.root: storage
title: BPIO_OUTFLAGS
ms.date: 07/08/2021
targetos: Windows
description: BPIO_OUTFLAGS defines the BypassIO output flags for the IOCTL_STORAGE_MANAGE_BYPASS_IO control code.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ntddstor.h
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
 - ntddstor.h
api_name:
 - _BPIO_OUTFLAGS
 - BPIO_OUTFLAGS
f1_keywords:
 - _BPIO_OUTFLAGS
 - ntddstor/_BPIO_OUTFLAGS
 - BPIO_OUTFLAGS
 - ntddstor/BPIO_OUTFLAGS
dev_langs:
 - c++
---

## -description

**BPIO_OUTFLAGS** defines the BypassIO output flags for the [**IOCTL_STORAGE_MANAGE_BYPASS_IO**](ni-ntddstor-ioctl_storage_manage_bypass_io.md) control code.

## -enum-fields

### -field BPIO_OUTFL_NONE

No output flag(s) are set.

## -remarks

See [BypassIO for storage drivers](/windows-hardware/drivers/storage/bypassio) for more information.

## -see-also

[**BPIO_OUTPUT**](ns-ntddstor-bpio_output.md)

[**IOCTL_STORAGE_MANAGE_BYPASS_IO**](ni-ntddstor-ioctl_storage_manage_bypass_io.md)
