---
UID: NF:acxmisc.AcxObjectBagRetrieveSizeT
tech.root: audio
title: AcxObjectBagRetrieveSizeT
ms.date: 01/28/2022
targetos: Windows
description: The AcxObjectBagRetrieveSizeT function retrieves a value from an existing, intialized AcxObjectBag that contains values. 
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
 - AcxObjectBagRetrieveSizeT
f1_keywords:
 - AcxObjectBagRetrieveSizeT
 - acxmisc/AcxObjectBagRetrieveSizeT
dev_langs:
 - c++
---

## -description

The AcxObjectBagRetrieveSizeT function retrieves a SizeT value from an existing, intialized AcxObjectBag that contains values. 

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

TBD - Example pending.

```cpp

```

## -see-also

[acxmisc.h header](index.md)

