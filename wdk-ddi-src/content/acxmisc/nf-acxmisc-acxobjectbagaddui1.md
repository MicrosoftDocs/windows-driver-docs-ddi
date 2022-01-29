---
UID: NF:acxmisc.AcxObjectBagAddUI1
tech.root: audio
title: AcxObjectBagAddUI1
ms.date: 01/10/2022
targetos: Windows
description: The AcxObjectBagAddUI1 function adds a UCHAR to and existing, intialized AcxObjectBag.
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
 - AcxObjectBagAddUI1
f1_keywords:
 - AcxObjectBagAddUI1
 - acxmisc/AcxObjectBagAddUI1
dev_langs:
 - c++
---

## -description

The AcxObjectBagAddUI1 function adds a UCHAR to and existing, intialized AcxObjectBag.
 
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

This example shows the use of AcxObjectBagAddUI1.

```cpp
NTSTATUS ObjBagAddDatapathId(
    _In_ ACXOBJECTBAG               ObjBag,
    _In_ UCHAR                      Id
)
{
    PAGED_CODE();

    NTSTATUS status = STATUS_SUCCESS;

    DECLARE_CONST_ACXOBJECTBAG_BLUETOOTH_PROPERTY_NAME(DatapathID);
    RETURN_NTSTATUS_IF_FAILED(AcxObjectBagAddUI1(ObjBag, &DatapathID, Id));
```

## -see-also

[acxmisc.h header](index.md)

