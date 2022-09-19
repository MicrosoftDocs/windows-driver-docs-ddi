---
UID: NF:acxcircuit.AcxCircuitGetPinById
tech.root: audio
title: AcxCircuitGetPinById
ms.date: 08/16/2021
targetos: Windows
description: When provided a valid PinID number, the AcxCircuitGetPinById function returns the corresponding ACXPIN object.
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
 - AcxCircuitGetPinById
f1_keywords:
 - AcxCircuitGetPinById
 - acxcircuit/AcxCircuitGetPinById
dev_langs:
 - c++
---

## -description

When provided a valid PinID number, the **AcxCircuitGetPinById** function returns the AcxCircuitGetPinById function returns the corresponding ACXPIN object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -parameters

### -param Circuit

An existing *ACXCIRCUIT* object.  

### -param PinId

A valid Pin ID number.

## -returns

A reference to an existing *ACXPIN* object.

## -remarks

### Example

Example usage is shown below.

```cpp
    const ULONG _BRIDGE_PIN_ID = 1;
    ACXPIN bridgePin = NULL;

    bridgePin = AcxCircuitGetPinById(Circuit, _BRIDGE_PIN_ID);
```

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)

