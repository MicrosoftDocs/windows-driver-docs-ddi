---
UID: NF:acxcircuit.AcxCircuitInitSetComponentId
tech.root: audio
title: AcxCircuitInitSetComponentId
ms.date: 02/01/2022
targetos: Windows
description: The AcxCircuitInitSetComponentId function sets the component ID for the ACXCIRCUIT.
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
 - AcxCircuitInitSetComponentId
f1_keywords:
 - AcxCircuitInitSetComponentId
 - acxcircuit/AcxCircuitInitSetComponentId
dev_langs:
 - c++
---

## -description

The **AcxCircuitInitSetComponentId** function sets the component ID for the ACXCIRCUIT.

## -parameters

### -param CircuitInit

The ACXCIRCUIT_INIT structure that defines the circuit initialization. ACXCIRCUIT_INIT is an opaque object used for circuit initialization. Use [AcxCircuitInitAllocate](nf-acxcircuit-acxcircuitinitallocate.md) to initialize the ACXCIRCUIT_INIT structure.

### -param ComponentId

A pointer to a defined GUID that serves as the component ID for the circuit. 

## -remarks

The driver must initialize the circuit's identity by setting the its URI (AcxCircuitInitAssignComponentUri) and/or its ID (this DDI).

### Example

Example usage is shown below.

```cpp
DEFINE_GUID(COMPONENT_GUID, 
0xf55ba68e, 0x4384, 0x4030, 0x97, 0x19, 0xec, 0xa4, 0xbe, 0x27, 0x6c, 0xc8);

    //
    // Add circuit identifiers.
    //
    AcxCircuitInitSetComponentId(CircuitInit, &COMPONENT_GUID);

    AcxCircuitInitAssignName(CircuitInit, &circuitName);
```

## -see-also

- [acxcircuit.h header](index.md)

READY2GO
