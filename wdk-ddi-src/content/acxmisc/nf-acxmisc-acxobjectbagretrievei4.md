---
UID: NF:acxmisc.AcxObjectBagRetrieveI4
tech.root: audio
title: AcxObjectBagRetrieveI4
ms.date: 01/10/2022
targetos: Windows
description: 
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
 - AcxObjectBagRetrieveI4
f1_keywords:
 - AcxObjectBagRetrieveI4
 - acxmisc/AcxObjectBagRetrieveI4
dev_langs:
 - c++
---

## -description

The function retrieves a value from an exisisting, intialized AcxObjectBag that contains values. 

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

TBD - Example pending.

This example shows the use of .

```cpp
    DECLARE_CONST_UNICODE_STRING(I4Str,    L"Value_I4");
 
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


    status |= AcxObjectBagAddI4(bag1, &I4Str, lValue);

    if (!NT_SUCCESS(status))
    {
        ASSERT(FALSE);
        goto exit;
    }

    // Read written values.
    status |= AcxObjectBagRetrieveI4(bag1, &I4Str, &lValue2);
```

## -see-also

[acxmisc.h header](index.md)

