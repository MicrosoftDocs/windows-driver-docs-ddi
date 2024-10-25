---
UID: NS:acxcircuit._ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS
tech.root: audio
title: ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS
ms.date: 09/30/2021
targetos: Windows
description: The ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS structure identifies the driver callbacks for ACX factory operations.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS, *PACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxcircuit.h
api_name:
 - _ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS
 - PACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS
 - ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS
f1_keywords:
 - _ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS
 - acxcircuit/_ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS
 - PACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS
 - acxcircuit/PACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS
 - ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS
 - acxcircuit/ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS
dev_langs:
 - c++
---

## -description

The **ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS** structure identifies the driver callbacks for ACX factory operations.

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field EvtAcxFactoryCircuitCreateCircuitDevice

The [EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUITDEVICE callback](nc-acxcircuit-evt_acx_factory_circuit_create_circuitdevice.md).

### -field EvtAcxFactoryCircuitDeleteCircuitDevice

The [ACX_FACTORY_CIRCUIT_DELETE_CIRCUITDEVICE callback](nc-acxcircuit-evt_acx_factory_circuit_delete_circuitdevice.md).

### -field EvtAcxFactoryCircuitCreateCircuit

The [EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUIT callback](nc-acxcircuit-evt_acx_factory_circuit_create_circuit.md).

## -remarks

### Example

Example usage is shown below.

```cpp
    ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS         operationCallbacks;
   
    //
    // Assign the circuit's operation-callbacks.
    //
    ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS_INIT(&operationCallbacks);
    operationCallbacks.EvtAcxFactoryCircuitCreateCircuitDevice = SdcaXu_EvtAcxFactoryCircuitCreateCircuitDevice;
    operationCallbacks.EvtAcxFactoryCircuitCreateCircuit = SdcaXu_EvtAcxFactoryCircuitCreateCircuit;
   
    AcxFactoryCircuitInitSetOperationCallbacks(factoryInit, &operationCallbacks);

```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)
