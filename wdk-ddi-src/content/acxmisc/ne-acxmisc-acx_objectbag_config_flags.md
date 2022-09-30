---
UID: NE:acxmisc._ACX_OBJECTBAG_CONFIG_FLAGS
tech.root: audio
title: ACX_OBJECTBAG_CONFIG_FLAGS
ms.date: 06/17/2022
targetos: Windows
description: The ACX_OBJECTBAG_CONFIG_FLAGS enumeration defines the configuration for an AcxObjectBag. 
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: acxmisc.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxmisc.h
api_name:
 - _ACX_OBJECTBAG_CONFIG_FLAGS
 - ACX_OBJECTBAG_CONFIG_FLAGS
f1_keywords:
 - _ACX_OBJECTBAG_CONFIG_FLAGS
 - acxmisc/_ACX_OBJECTBAG_CONFIG_FLAGS
 - ACX_OBJECTBAG_CONFIG_FLAGS
 - acxmisc/ACX_OBJECTBAG_CONFIG_FLAGS
dev_langs:
 - c++
---

## -description

The **ACX_OBJECTBAG_CONFIG_FLAGS** enumeration defines the configuration for an AcxObjectBag. 

## -enum-fields

### -field AcxObjectBagConfigNoFlags

Indicates that no config flags are set.

### -field AcxObjectBagConfigEnableReads

Indicates that reads are enabled.

### -field AcxObjectBagConfigEnableWrites

Indicates that writes are enabled.

### -field AcxObjectBagConfigFailIfExist

Indicates that if an ACXOBJECTBAG with the same identity is already present, creation should fail instead of opening the existing one.

### -field AcxObjectBagConfigOpenWithHandle

Indicates to open the ACXOBJECTBAG whose handle is specified in the configuration stracture.

### -field AcxObjectBagConfigValidFlags

For internal validation, do not use.


## -remarks

### Example

This example shows the use of ACX_OBJECTBAG_CONFIG_FLAGS.

```cpp
        GUID                    uniqueId = { 0 };
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
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxmisc.h header](index.md)
