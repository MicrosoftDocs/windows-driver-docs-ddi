---
UID: NF:acxmisc.AcxObjectBagAddUI4
tech.root: audio
title: AcxObjectBagAddUI4
ms.date: 01/10/2022
targetos: Windows
description: The AcxObjectBagAddUI4 function adds a UI4 data to an existing intialized AcxObjectBag. 
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
 - AcxObjectBagAddUI4
f1_keywords:
 - AcxObjectBagAddUI4
 - acxmisc/AcxObjectBagAddUI4
dev_langs:
 - c++
---

## -description

The AcxObjectBagAddUI4 function adds a UI4 data to an existing intialized AcxObjectBag. 

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

This example shows the use of AcxObjectBagAddUI4.

TBD - Need to validate fabricated sample code.


```cpp
    DECLARE_CONST_ACXOBJECTBAG_DRIVER_PROPERTY_NAME(VendorX, TestUI4);
    RETURN_NTSTATUS_IF_FAILED(AcxObjectBagAddUI4(objBag, &TestUI4, _DSP_STREAM_PROPERTY_UI4_VALUE));
```

## -see-also

[acxmisc.h header](index.md)

READY2GO
