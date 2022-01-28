---
UID: NF:acxmisc.AcxObjectBagAddI2
tech.root: audio
title: AcxObjectBagAddI2
ms.date: 01/10/2022
targetos: Windows
description: The AcxObjectBagAddI2 function adds a unicode string to an exisisting, intialized AcxObjectBag. 
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
 - AcxObjectBagAddI2
f1_keywords:
 - AcxObjectBagAddI2
 - acxmisc/AcxObjectBagAddI2
dev_langs:
 - c++
---

## -description

The AcxObjectBagAddI2 function adds a unicode string to an exisisting, intialized AcxObjectBag. 

## -parameters

### -param ObjectBag

An intialized ObjectBag ACX object. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ValueName

The name of the value that will be used to access the value.

### -param Value

The Value to be added to the ObjectBag.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

This example shows the use of AcxObjectBagAddI2.

```cpp
    DECLARE_CONST_UNICODE_STRING(I2Str,    L"Value_I2");

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

    status = AcxObjectBagAddI2(bag1, &I2Str, cValue);
```

## -see-also

[acxmisc.h header](index.md)

