---
UID: NF:acxcircuit.AcxCircuitInitAssignAcxCreateStreamCallback
tech.root: audio
title: AcxCircuitInitAssignAcxCreateStreamCallback
ms.date: 08/16/2021
targetos: Windows
description: The AcxCircuitInitAssignAcxCreateStreamCallback function is used to assign an Acx CreateStream callback.
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
 - AcxCircuitInitAssignAcxCreateStreamCallback
f1_keywords:
 - AcxCircuitInitAssignAcxCreateStreamCallback
 - acxcircuit/AcxCircuitInitAssignAcxCreateStreamCallback
dev_langs:
 - c++
---

## -description

The AcxCircuitInitAssignAcxCreateStreamCallback function is used to assign an ACX CreateStream callback.

## -parameters

### -param CircuitInit

The ACXCIRCUIT_INIT structure that defines the circuit initialization. ACXCIRCUIT_INIT is an opaque object used for circuit initialization. Use [AcxCircuitInitAllocate](nf-acxcircuit-acxcircuitinitallocate.md) to initialize the ACXCIRCUIT_INIT structure.

### -param EvtCircuitCreateStream

A pointer to a [EVT_ACX_CIRCUIT_CREATE_STREAM](nc-acxcircuit-evt_acx_circuit_create_stream.md) callback. 

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp

    //
    // Get a CircuitInit structure.
    //
    circuitInit = AcxCircuitInitAllocate(Device);

    //
    // Assign the circuit's pnp-power callbacks.
    //
    ACX_CIRCUIT_PNPPOWER_CALLBACKS_INIT(&powerCallbacks);
    powerCallbacks.EvtAcxCircuitPowerUp = CodecC_EvtCircuitPowerUp;
    powerCallbacks.EvtAcxCircuitPowerDown = CodecC_EvtCircuitPowerDown;
    AcxCircuitInitSetAcxCircuitPnpPowerCallbacks(circuitInit, &powerCallbacks);

    //
    // Set circuit-callbacks.
    //
    status = AcxCircuitInitAssignAcxRequestPreprocessCallback(
                                            circuitInit, 
                                            CodecC_EvtCircuitRequestPreprocess,
                                            (ACXCONTEXT)AcxRequestTypeAny, // dbg only
                                            AcxRequestTypeAny,
                                            NULL, 
                                            AcxItemIdNone);

    status = AcxCircuitInitAssignAcxCreateStreamCallback(
                                            circuitInit, 
                                            CodecC_EvtCircuitCreateStream);

```

## -see-also

- [acxcircuit.h header](index.md)

TBD - Please review this topic