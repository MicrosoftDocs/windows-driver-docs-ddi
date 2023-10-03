---
UID: NF:acxmisc.AcxObjectBagAddBlob
tech.root: audio
title: AcxObjectBagAddBlob
ms.date: 12/16/2022
targetos: Windows
description: The AcxObjectBagAddBlob function adds blob data to an existing, initialized AcxObjectBag.
prerelease: false
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
 - AcxObjectBagAddBlob
f1_keywords:
 - AcxObjectBagAddBlob
 - acxmisc/AcxObjectBagAddBlob
dev_langs:
 - c++
---

## -description

The **AcxObjectBagAddBlob** function adds blob data to an existing, initialized AcxObjectBag.

## -parameters

### -param ObjectBag

An initialized ObjectBag ACX object. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ValueName

The name of the value that will be used to access the value.

### -param Value

The Value to be added to the ObjectBag.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

This example shows the use of AcxObjectBagAddBlob.

```cpp
    NTSTATUS status = STATUS_SUCCESS;

    DECLARE_CONST_ACXOBJECTBAG_DRIVER_PROPERTY_NAME(VendorX, PropertiesBlock);
    WDFMEMORY blobMem;
    RETURN_NTSTATUS_IF_FAILED(WdfMemoryCreatePreallocated(NULL, Buffer, SizeCb, &blobMem));
    RETURN_NTSTATUS_IF_FAILED(AcxObjectBagAddBlob(ObjBag, &PropertiesBlock, blobMem));
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxmisc.h header](index.md)
