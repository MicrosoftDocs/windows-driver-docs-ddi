---
UID: NF:acxmisc.AcxObjectBagRetrieveBlob
tech.root: audio
title: AcxObjectBagRetrieveBlob
ms.date: 06/17/2022
targetos: Windows
description: The AcxObjectBagRetrieveBlob function retrieves a blob value from an existing, intialized AcxObjectBag that contains values. 
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
 - AcxObjectBagRetrieveBlob
f1_keywords:
 - AcxObjectBagRetrieveBlob
 - acxmisc/AcxObjectBagRetrieveBlob
dev_langs:
 - c++
---

## -description

The AcxObjectBagRetrieveBlob function retrieves a blob value from an existing, intialized AcxObjectBag that contains values. 

## -parameters

### -param ObjectBag

An intialized ObjectBag ACX object. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ValueName

The name of the value that will be used to access the value.

### -param ValueAttributes

Optional WDF_OBJECT_ATTRIBUTES that can be used to define additional ValueAttributes. 

### -param Value

The Value to be retrieved from the ObjectBag.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

This example shows the use of AcxObjectBagRetrieveBlob.

```cpp
    WDFMEMORY vendorPropertiesBlock = NULL;
    PVOID vendorPropertiesBuffer = NULL;
    size_t vendorPropertiesSize = 0;
    NTSTATUS status = STATUS_NOT_FOUND;

    PAGED_CODE();

    //
    // Retrieve the vendor blob from the CircuitProperties object bag. 
    //
    RETURN_NTSTATUS_IF_FAILED(AcxObjectBagRetrieveBlob(CircuitProperties, &VendorPropertiesBlock, NULL, &vendorPropertiesBlock));

    vendorPropertiesBuffer = WdfMemoryGetBuffer(vendorPropertiesBlock, &vendorPropertiesSize);
```

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxmisc.h header](index.md)
