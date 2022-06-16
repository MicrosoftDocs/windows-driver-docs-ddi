---
UID: NF:acxcircuit.AcxCircuitCreate
tech.root: audio
title: AcxCircuitCreate
ms.date: 06/09/2022
targetos: Windows
description: The AcxCircuitCreate function is used to create an ACXCIRCUIT.
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
 - AcxCircuitCreate
f1_keywords:
 - AcxCircuitCreate
 - acxcircuit/AcxCircuitCreate
dev_langs:
 - c++
---

## -description

The **AcxCircuitCreate** function is used to create an ACXCIRCUIT.

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that will be associated with the circuit. 

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) that are used to set the various object’s values: cleanup and destroy callbacks, context type, and to specify its parent WDF object.

### -param Config

The ACXCIRCUIT_INIT structure that defines the circuit factory initialization. ACXCIRCUIT_INIT is an opaque object used for circuit factory initialization. Use [AcxCircuitInitAllocate](nf-acxcircuit-acxcircuitinitallocate.md) to initialize the ACXCIRCUIT_INIT structure.

### -param Circuit

A pointer to a location that receives a handle to the new ACXCIRCUIT Object.  For more information, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).


## -remarks

An ACXCIRCUIT represents a full or partial (multi-circuit) audio path to a user perceived audio device (speakers, mic, etc.). 
An ACXCIRCUIT has at least one input pin (ACXPIN) and one output pin (ACXPIN), and it may aggregate one or more ACXELEMENTS objects. By default, ACXELEMENTs are ‘connected’ in the same order of assembly. 

### Example

Example usage is shown below.

```cpp
    status = AcxCircuitInitAssignName(circuitInit, &circuitName);
    //
    // Add circuit type.
    //
    AcxCircuitInitSetCircuitType(circuitInit, AcxCircuitTypeRender);

    //
    // Assign the circuit's pnp-power callbacks.
    //
    ACX_CIRCUIT_PNPPOWER_CALLBACKS_INIT(&powerCallbacks);
    powerCallbacks.EvtAcxCircuitPowerUp = SdcaR_EvtCircuitPowerUp;
    powerCallbacks.EvtAcxCircuitPowerDown = SdcaR_EvtCircuitPowerDown;
    
    AcxCircuitInitSetAcxCircuitPnpPowerCallbacks(circuitInit, &powerCallbacks);

    //
    // Set circuit-callbacks.
    //
    status = AcxCircuitInitAssignAcxCreateStreamCallback(
                                            circuitInit, 
                                            SdcaR_EvtCircuitCreateStream);
    
    //
    // Create the circuit.
    //
    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, SDCA_RENDER_CIRCUIT_CONTEXT);   
    status = AcxCircuitCreate(Device, &attributes, &circuitInit, &circuit);
```

## -see-also

- [acxcircuit.h header](index.md)

READY2GO
