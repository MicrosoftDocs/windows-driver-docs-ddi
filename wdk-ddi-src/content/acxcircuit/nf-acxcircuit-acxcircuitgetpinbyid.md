---
UID: NF:acxcircuit.AcxCircuitGetPinById
tech.root: audio
title: AcxCircuitGetPinById
ms.date: 08/16/2021
targetos: Windows
description: When provided a valid PinID number, the AcxCircuitGetPinById function returns a reference to an existing ACXPIN object.
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
When provided a valid PinID number, the AcxCircuitGetPinById function returns a reference to an existing ACXPIN object. (DocsTeam - need link to ACX Object Summary topic).

## -parameters

### -param Circuit

TBD - An existing ACXCIRCUIT circuit object.  (DocsTeam - need link to ACX Object Summary topic).

### -param PinId

The Pin ID number. This is a TBD zero/one based count. 

## -returns

A reference to an existing ACXPIN object.  (DocsTeam - need link to ACX Object Summary topic).

## -remarks

### Example

Example usage is shown below.

```cpp
    const ULONG _BRIDGE_PIN_ID = 1;
    ACXPIN bridgePin = NULL;

    bridgePin = AcxCircuitGetPinById(Circuit, _BRIDGE_PIN_ID);
```

## -see-also

[acxcircuit.h header](index.md)

