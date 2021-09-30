---
UID: NS:acxcircuit._ACX_CIRCUIT_COMPOSITE_CALLBACKS
tech.root: audio
title: ACX_CIRCUIT_COMPOSITE_CALLBACKS
ms.date: 07/19/2021
targetos: Windows
description: The ACX_CIRCUIT_COMPOSITE_CALLBACKS structure identifies the driver callbacks for ACX composite circuit  operations.
prerelease: true
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
req.typenames: ACX_CIRCUIT_COMPOSITE_CALLBACKS, *PACX_CIRCUIT_COMPOSITE_CALLBACKS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxcircuit.h
api_name:
 - _ACX_CIRCUIT_COMPOSITE_CALLBACKS
 - PACX_CIRCUIT_COMPOSITE_CALLBACKS
 - ACX_CIRCUIT_COMPOSITE_CALLBACKS
f1_keywords:
 - _ACX_CIRCUIT_COMPOSITE_CALLBACKS
 - acxcircuit/_ACX_CIRCUIT_COMPOSITE_CALLBACKS
 - PACX_CIRCUIT_COMPOSITE_CALLBACKS
 - acxcircuit/PACX_CIRCUIT_COMPOSITE_CALLBACKS
 - ACX_CIRCUIT_COMPOSITE_CALLBACKS
 - acxcircuit/ACX_CIRCUIT_COMPOSITE_CALLBACKS
dev_langs:
 - c++
---

## -description

The ACX_CIRCUIT_COMPOSITE_CALLBACKS structure identifies the driver callbacks for ACX composite circuit  operations.

## -struct-fields

### -field Size

The length, in bytes, of this structure. 

### -field EvtAcxCircuitCompositeCircuitInitialize

The [EVT_ACX_CIRCUIT_COMPOSITE_CIRCUIT_INITIALIZE callback](nc-acxcircuit-evt_acx_circuit_composite_circuit_initialize.md).

### -field EvtAcxCircuitCompositeInitialize

The [EVT_ACX_CIRCUIT_COMPOSITE_INITIALIZE callback](nc-acxcircuit-evt_acx_circuit_composite_initialize.md).

### -field EvtAcxCircuitCompositeDeinitialize

The [EVT_ACX_CIRCUIT_COMPOSITE_DEINITIALIZE callback](nc-acxcircuit-evt_acx_circuit_composite_deinitialize.md).

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

## -see-also

[acxcircuit.h header](index.md)

READY2GO