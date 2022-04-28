---
UID: NF:acxcircuit.AcxCircuitInitAssignName
tech.root: audio
title: AcxCircuitInitAssignName
ms.date: 08/17/2021
targetos: Windows
description: The AcxCircuitInitAssignName function assigns a friendly Name that will be used for the circuit initialization.
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
 - AcxCircuitInitAssignName
f1_keywords:
 - AcxCircuitInitAssignName
 - acxcircuit/AcxCircuitInitAssignName
dev_langs:
 - c++
---

## -description

The AcxCircuitInitAssignName function assigns a friendly Name that will be used for the circuit initialization.

## -parameters

### -param CircuitInit

The ACXCIRCUIT_INIT structure that defines the circuit initialization. ACXCIRCUIT_INIT is an opaque object used for circuit initialization. Use [AcxCircuitInitAllocate](nf-acxcircuit-acxcircuitinitallocate.md) to initialize the ACXCIRCUIT_INIT structure.

### -param CircuitName

A unicode string describes the circuit, such as *Microphone0*  that is used as a friendly name for the circuit.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
    // Circuit Name
    DECLARE_CONST_UNICODE_STRING(circuitName, L"Microphone0");

    //
    // Add circuit identifiers.
    //
    AcxCircuitInitSetComponentId(CircuitInit, &COMPONENT_GUID);

    AcxCircuitInitAssignName(CircuitInit, &circuitName);
```

## -see-also

- [acxcircuit.h header](index.md)

TBD - Please review this topic