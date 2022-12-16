---
UID: NF:acxmisc.ACX_OBJECTBAG_CONFIG_INIT
tech.root: audio
title: ACX_OBJECTBAG_CONFIG_INIT
ms.date: 06/17/2022
targetos: Windows
description: The ACX_OBJECTBAG_CONFIG_INIT function initializes an ACX_OBJECTBAG_CONFIG structure.
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
 - LibDef
api_location:
 - acxmisc.h
api_name:
 - ACX_OBJECTBAG_CONFIG_INIT
f1_keywords:
 - ACX_OBJECTBAG_CONFIG_INIT
 - acxmisc/ACX_OBJECTBAG_CONFIG_INIT
dev_langs:
 - c++
---

## -description

The ACX_OBJECTBAG_CONFIG_INIT function initializes an [ACX_OBJECTBAG_CONFIG](ns-acxmisc-acx_objectbag_config.md) structure.

## -parameters

### -param Config

A pointer to the [ACX_OBJECTBAG_CONFIG](ns-acxmisc-acx_objectbag_config.md) structure that will be initialized.

## -remarks

### Example

This example shows the use of ACX_OBJECTBAG_CONFIG_INIT.

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
        auto objBag_free = scope_exit([&objBag]() {
            WdfObjectDelete(objBag);
            });

        RETURN_NTSTATUS_IF_FAILED(AcxObjectBagRetrieveGuid(objBag, &UniqueID, &uniqueId));

        RETURN_NTSTATUS_IF_FAILED(RtlStringFromGUID(uniqueId, &uniqueIdStr));
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxmisc.h header](index.md)
