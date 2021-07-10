---
UID: NE:ntddstor._BPIO_INFLAGS
tech.root: storage
title: BPIO_INFLAGS
ms.date: 07/08/2021
targetos: Windows
description: BPIO_INFLAGS defines the BypassIO input flags for the IOCTL_STORAGE_MANAGE_BYPASS_IO control code.
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
 - _BPIO_INFLAGS
 - BPIO_INFLAGS
f1_keywords:
 - _BPIO_INFLAGS
 - ntddstor/_BPIO_INFLAGS
 - BPIO_INFLAGS
 - ntddstor/BPIO_INFLAGS
dev_langs:
 - c++
---

## -description

**BPIO_INFLAGS** defines the BypassIO input flags for the [**IOCTL_STORAGE_MANAGE_BYPASS_IO**](ni-ntddstor-ioctl_storage_manage_bypass_io.md) control code.

## -enum-fields

### -field BPIO_INFL_NONE

No input flag(s) are set.

## -remarks

See [BypassIO for storage drivers](/windows-hardware/drivers/storage/stornvme-feature-support/bypassio) for more information.

## -see-also

[**BPIO_INPUT**](ns-ntddstor-bpio_input.md)

[**IOCTL_STORAGE_MANAGE_BYPASS_IO**](ni-ntddstor-ioctl_storage_manage_bypass_io.md)
