---
UID: NF:acxmisc.AcxObjectBagRetrieveUI2
tech.root: audio
title: AcxObjectBagRetrieveUI2
ms.date: 02/23/2022
targetos: Windows
description: The AcxObjectBagRetrieveUI2 function retrieves a unsigned int two byte UI2 (USHORT) from an existing, intialized AcxObjectBag that contains values. 
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
 - AcxObjectBagRetrieveUI2
f1_keywords:
 - AcxObjectBagRetrieveUI2
 - acxmisc/AcxObjectBagRetrieveUI2
dev_langs:
 - c++
---

## -description

The AcxObjectBagRetrieveUI2 function retrieves a unsigned int two byte UI2 (USHORT) from an existing, intialized AcxObjectBag that contains values. 

## -parameters

### -param ObjectBag

An intialized ObjectBag ACX object. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ValueName

The name of the value that will be used to access the value.

### -param Value

The Value to be retrieved from the ObjectBag.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

This example shows the use of AcxObjectBagRetrieveUI2.

```cpp
    ACXOBJECTBAG objBag     = NULL;
    USHORT       ui2Value   = 0;

    //Initialize an object bag configuration
    ACX_OBJECTBAG_CONFIG objBagCfg;
    ACX_OBJECTBAG_CONFIG_INIT(&objBagCfg);
    
    // Set the WDF attributes, and create an object bag 
    WDF_OBJECT_ATTRIBUTES_INIT(&attributes);
    attributes.ParentObject = Circuit;
    RETURN_NTSTATUS_IF_FAILED(AcxObjectBagCreate(&attributes, &objBagCfg, &objBag));

    // Enable deletion of the object bag when the function completes and goes out of scope
    auto objBag_scope = scope_exit([&objBag]() {
        if (objBag != NULL)
        {
            WdfObjectDelete(objBag);
        }
    });

    //Create Properties and add them to an object bag
    DECLARE_CONST_ACXOBJECTBAG_DRIVER_PROPERTY_NAME(VendorX, TestUI2);

    ui2Value = 0x55;
    RETURN_NTSTATUS_IF_FAILED(AcxObjectBagAddUI2(objBag, &TestUI2, ui2Value)

    // Retrieve the value from the object bag
    ui2Value = 0;
    RETURN_NTSTATUS_IF_FAILED(AcxObjectBagRetrieveUI2(objBag, &TestUI2, &ui2Value));
```

## -see-also

[acxmisc.h header](index.md)

