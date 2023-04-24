---
UID: NS:acxmisc._ACX_OBJECTBAG_CONFIG
tech.root: audio
title: ACX_OBJECTBAG_CONFIG
ms.date: 07/01/2022
targetos: Windows
description: The ACX_OBJECTBAG_CONFIG structure defines the configuration for an AcxObjectBag.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxmisc.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_OBJECTBAG_CONFIG, *PACX_OBJECTBAG_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxmisc.h
api_name:
 - _ACX_OBJECTBAG_CONFIG
 - PACX_OBJECTBAG_CONFIG
 - ACX_OBJECTBAG_CONFIG
f1_keywords:
 - _ACX_OBJECTBAG_CONFIG
 - acxmisc/_ACX_OBJECTBAG_CONFIG
 - PACX_OBJECTBAG_CONFIG
 - acxmisc/PACX_OBJECTBAG_CONFIG
 - ACX_OBJECTBAG_CONFIG
 - acxmisc/ACX_OBJECTBAG_CONFIG
dev_langs:
 - c++
---

## -description

The ACX_OBJECTBAG_CONFIG structure defines the configuration for an AcxObjectBag.

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field Flags

Bitwise OR of [ACX_OBJECTBAG_FLAGS](ne-acxmisc-acx_objectbag_config_flags.md) that is used to configure the object bag.

### -field ParentKey

The ParentKey of the ObjectBag.

### -field Name

The name of the ObjectBag that is used to access it.

### -field Handle

The the ObjectBag handle that is used to access the object bag.

## -remarks

### Example

This example shows the use of ACX_OBJECTBAG_CONFIG.

```cpp
        UNICODE_STRING          uniqueIdStr = { 0 };
        UNICODE_STRING          pnpDeviceId = { 0 };
        ACX_OBJECTBAG_CONFIG    objBagCfg;

        DECLARE_CONST_ACXOBJECTBAG_SYSTEM_PROPERTY_NAME(UniqueID);

        ACX_OBJECTBAG_CONFIG_INIT(&objBagCfg);
        objBagCfg.Handle = CircuitConfig->CompositeProperties;
        objBagCfg.Flags |= AcxObjectBagConfigOpenWithHandle;

        WDF_OBJECT_ATTRIBUTES_INIT(&attributes);
        ACXOBJECTBAG objBag = NULL;

        RETURN_NTSTATUS_IF_FAILED(AcxObjectBagOpen(&attributes, &objBagCfg, &objBag));
        auto objBag_free = scope_exit([&objBag]() {
            WdfObjectDelete(objBag);
            });

        RETURN_NTSTATUS_IF_FAILED(AcxObjectBagRetrieveGuid(objBag, &UniqueID, &uniqueId));
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxmisc.h header](index.md)
