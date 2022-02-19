---
UID: NF:acxmisc.AcxObjectBagRetrieveI8
tech.root: audio
title: AcxObjectBagRetrieveI8
ms.date: 02/18/2022
targetos: Windows
description: The AcxObjectBagRetrieveI8 function retrieves a ULONG64 value from an existing, intialized AcxObjectBag that contains values.
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
 - AcxObjectBagRetrieveI8
f1_keywords:
 - AcxObjectBagRetrieveI8
 - acxmisc/AcxObjectBagRetrieveI8
dev_langs:
 - c++
---

## -description

The AcxObjectBagRetrieveI8 function retrieves a ULONG64 value value from an existing, intialized AcxObjectBag that contains values.

## -parameters

### -param ObjectBag

An intialized ObjectBag ACX object. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ValueName

The name of the value that will be used to access the value.

### -param Value

The unicode string Value to be retrieved from the ObjectBag.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

This example shows the use of AcxObjectBagRetrieveI8.

```cpp
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

    // Add something to the bag
    status = AcxObjectBagAddUI8(bag1, &UI8Str, ul64Value);

    if (!NT_SUCCESS(status))
    {
        ASSERT(FALSE);
        goto exit;
    }

    // Read written values.
    status = AcxObjectBagRetrieveUI8(bag1, &UI8Str, &ul64Value2);
```

## -see-also

[acxmisc.h header](index.md)

