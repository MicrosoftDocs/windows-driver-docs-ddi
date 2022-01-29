---
UID: NF:acxmisc.AcxObjectBagAddBlob
tech.root: audio
title: AcxObjectBagAddBlob
ms.date: 01/27/2022
targetos: Windows
description: The AcxObjectBagAddBlob function adds blob data to an existing, intialized AcxObjectBag. 
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
 - AcxObjectBagAddBlob
f1_keywords:
 - AcxObjectBagAddBlob
 - acxmisc/AcxObjectBagAddBlob
dev_langs:
 - c++
---

## -description

The AcxObjectBagAddBlob function adds blob data to an existing, intialized AcxObjectBag. 

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

This example shows the use of AcxObjectBagAddBlob.

TBD - Is this example code OK?

```cpp
    NTSTATUS status = STATUS_SUCCESS;

    DECLARE_CONST_ACXOBJECTBAG_SYSTEM_PROPERTY_NAME(VendorPropertiesBlock);
    STRING vendorBlob;
    RtlInitString(&vendorBlob, Blob);
    WDFMEMORY vendorBlobMem;
    RETURN_NTSTATUS_IF_FAILED(WdfMemoryCreatePreallocated(NULL, vendorBlob.Buffer, vendorBlob.MaximumLength, &vendorBlobMem));
    RETURN_NTSTATUS_IF_FAILED(AcxObjectBagAddBlob(ObjBag, &VendorPropertiesBlock, vendorBlobMem));

```

## -see-also

[acxmisc.h header](index.md)

