---
UID: NF:acxcircuit.AcxCircuitGetElementById
tech.root: audio
title: AcxCircuitGetElementById
ms.date: 08/16/2021
targetos: Windows
description: When provided a valid ElementID number, the AcxCircuitGetElementById function returns a reference to an existing ACXELEMENT object.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
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
 - HeaderDef
api_location:
 - acxcircuit.h
api_name:
 - AcxCircuitGetElementById
f1_keywords:
 - AcxCircuitGetElementById
 - acxcircuit/AcxCircuitGetElementById
dev_langs:
 - c++
---

## -description

When provided a valid ElementID number, the AcxCircuitGetElementById function returns a reference to an existing ACXELEMENT object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -parameters

### -param Circuit

TBD - An existing ACXCIRCUIT circuit object. 

### -param ElementId

The Element ID number. This is a TBD zero/one based count. 

## -returns

An existing ACXELEMENT object.  

## -remarks

### Example

Example usage is shown below.

```cpp
    ACXELEMENT              element     = nullptr;
    ULONGLONG               index       = GetMessageContext(Event); // Context is an index.

    element = AcxCircuitGetElementById(Circuit, (ULONG)index);
```

## -see-also

[acxcircuit.h header](index.md)

