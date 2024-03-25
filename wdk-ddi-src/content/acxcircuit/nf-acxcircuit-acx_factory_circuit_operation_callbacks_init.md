---
UID: NF:acxcircuit.ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS_INIT
tech.root: audio
title: ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS_INIT
ms.date: 07/28/2022
targetos: Windows
description: The ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS_INIT function initializes a ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS config structure.
prerelease: false
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
 - ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS_INIT
f1_keywords:
 - ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS_INIT
 - acxcircuit/ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS_INIT
dev_langs:
 - c++
---

## -description

The **ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS_INIT** function initializes a 
[ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS](ns-acxcircuit-acx_factory_circuit_operation_callbacks.md) config structure. No inputs are used with this function.

## -parameters

### -param Config

An initialized [ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS](ns-acxcircuit-acx_factory_circuit_operation_callbacks.md) config structure that is used to store circuit factory operation callbacks information.

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

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)
