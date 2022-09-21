---
UID: NF:acxmisc.DECLARE_CONST_ACXOBJECTBAG_DRIVER_PROPERTY_NAME
tech.root: audio
title: DECLARE_CONST_ACXOBJECTBAG_DRIVER_PROPERTY_NAME
ms.date: 06/17/2022
targetos: Windows
description: The DECLARE_CONST_ACXOBJECTBAG_DRIVER_PROPERTY_NAME function declares an ACX object bag property name. 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxmisc.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxmisc.h
api_name:
 - DECLARE_CONST_ACXOBJECTBAG_DRIVER_PROPERTY_NAME
f1_keywords:
 - DECLARE_CONST_ACXOBJECTBAG_DRIVER_PROPERTY_NAME
 - acxmisc/DECLARE_CONST_ACXOBJECTBAG_DRIVER_PROPERTY_NAME
dev_langs:
 - c++
---

## -description

The DECLARE_CONST_ACXOBJECTBAG_DRIVER_PROPERTY_NAME function declares an ACX object bag property name. Driver defined properties start with `drv_<ven>_`.

## -parameters

### -param ven

The vendor ID that identifies the vendor.

### -param name

The name of the declared ACX object bag property name.

## -remarks

### Example

This example shows the use of DECLARE_CONST_ACXOBJECTBAG_DRIVER_PROPERTY_NAME.

```cpp
    DECLARE_CONST_ACXOBJECTBAG_DRIVER_PROPERTY_NAME(VendorX, TestUI4);
```

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxmisc.h header](index.md)
