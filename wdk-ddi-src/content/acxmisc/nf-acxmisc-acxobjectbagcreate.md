---
UID: NF:acxmisc.AcxObjectBagCreate
tech.root: audio
title: AcxObjectBagCreate
ms.date: 12/16/2022
targetos: Windows
description: The AcxObjectBagCreate function creates a new AcxObjectBag.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxmisc.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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
 - AcxObjectBagCreate
f1_keywords:
 - AcxObjectBagCreate
 - acxmisc/AcxObjectBagCreate
dev_langs:
 - c++
---

## -description

The AcxObjectBagCreate function creates a new AcxObjectBag.

## -parameters

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure that are used to set various object's values: cleanup and destroy callbacks, context type, and to specify its parent object.

### -param Config

A pointer to the initialized [ACX_OBJECTBAG_CONFIG](ns-acxmisc-acx_objectbag_config.md) structure.

### -param ObjectBag

An initialized ObjectBag ACX object. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

This example shows the use of AcxObjectBagCreate.

```cpp
    DECLARE_CONST_UNICODE_STRING(I1Str,    L"Value_I1");

    // Create a simple object.
    ACX_OBJECTBAG_CONFIG_INIT(&cfg1);
    WDF_OBJECT_ATTRIBUTES_INIT(&attr);
    attr.ParentObject = WdfGetDriver();
    
    status = AcxObjectBagCreate(&attr, &cfg1, &bag1);
    if (!NT_SUCCESS(status))
    {
        ASSERT(FALSE);
        goto exit;
    }

    // Add something to the object bag
    status = AcxObjectBagAddI1(bag1, &I1Str, cValue);
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxmisc.h header](index.md)
