---
UID: NF:acxmisc.AcxObjectBagAddI8
tech.root: audio
title: AcxObjectBagAddI8
ms.date: 01/28/2022
targetos: Windows
description: The AcxObjectBagAddI8 function adds a ULONG64 value to an existing, intialized AcxObjectBag. 
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
 - AcxObjectBagAddI8
f1_keywords:
 - AcxObjectBagAddI8
 - acxmisc/AcxObjectBagAddI8
dev_langs:
 - c++
---

## -description

The AcxObjectBagAddI8 function adds a I8 data TBD ULONG64 value to an existing, intialized AcxObjectBag. 

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

This example shows the use of AcxObjectBagAddI8.

```cpp
    DECLARE_CONST_ACXOBJECTBAG_DRIVER_PROPERTY_NAME(VendorX, TestI8);
    RETURN_NTSTATUS_IF_FAILED(AcxObjectBagAddI8(objBag, &TestI8, _DSP_STREAM_PROPERTY_I8_VALUE));

```

## -see-also

[acxmisc.h header](index.md)

READY2GO
