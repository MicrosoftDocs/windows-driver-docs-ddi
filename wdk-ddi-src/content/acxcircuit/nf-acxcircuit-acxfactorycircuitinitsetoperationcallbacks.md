---
UID: NF:acxcircuit.AcxFactoryCircuitInitSetOperationCallbacks
tech.root: audio
title: AcxFactoryCircuitInitSetOperationCallbacks
ms.date: 08/20/2021
targetos: Windows
description: TBD - The AcxFactoryCircuitInitSetOperationCallbacks sets the OperationCallbacks for Acx Circuit Factory initialization operations.
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
 - AcxFactoryCircuitInitSetOperationCallbacks
f1_keywords:
 - AcxFactoryCircuitInitSetOperationCallbacks
 - acxcircuit/AcxFactoryCircuitInitSetOperationCallbacks
dev_langs:
 - c++
---

## -description

The AcxFactoryCircuitInitSetOperationCallbacks sets the OperationCallbacks for Acx Circuit Factory initialization operations.

## -parameters

### -param FactoryInit

An ACXFACTORYCIRCUIT_INIT structure that is used for circuit factory initialization. This is an opaque structure that is used to store ACX Circuit factory initialization information and associate the factory with a WDF device.
Use the [AcxFactoryCircuitInitAllocate function](nf-acxcircuit-acxfactorycircuitinitallocate.md) to initialize the ACXFACTORYCIRCUIT_INIT structure.

### -param EvtOperationCallbacks

An [ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS structure](ns-acxcircuit-acx_factory_circuit_operation_callbacks.md) that identifies the driver callbacks for ACX factory operations.

## -remarks

### Example

Example usage is shown below.

```cpp
    //
    // Get a FactoryCircuitInit structure.
    //
    PACXFACTORYCIRCUIT_INIT factoryInit = NULL;
    factoryInit = AcxFactoryCircuitInitAllocate(Device);

    //
    // Add factory identifiers.
    //
    RETURN_NTSTATUS_IF_FAILED(AcxFactoryCircuitInitAssignComponentUri(factoryInit, &dspFactoryUri));
    RETURN_NTSTATUS_IF_FAILED(AcxFactoryCircuitInitAssignName(factoryInit, &dspFactoryName));

    //
    // Assign the circuit's operation-callbacks.
    //
    ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS operationCallbacks;
    ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS_INIT(&operationCallbacks);

    operationCallbacks.EvtAcxFactoryCircuitCreateCircuitDevice = Dsp_EvtAcxFactoryCircuitCreateCircuitDevice;
    operationCallbacks.EvtAcxFactoryCircuitCreateCircuit = Dsp_EvtAcxFactoryCircuitCreateCircuit;
    AcxFactoryCircuitInitSetOperationCallbacks(factoryInit, &operationCallbacks);
```

## -see-also

[acxcircuit.h header](index.md)

