---
UID: NF:acxcircuit.AcxCircuitInitAssignAcxRequestPreprocessCallback
tech.root: audio
title: AcxCircuitInitAssignAcxRequestPreprocessCallback
ms.date: 08/27/2021
targetos: Windows
description: The AcxCircuitInitAssignAcxRequestPreprocessCallback function initializes defined AssignAcxRequest Preprocess callbacks.
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
 - AcxCircuitInitAssignAcxRequestPreprocessCallback
f1_keywords:
 - AcxCircuitInitAssignAcxRequestPreprocessCallback
 - acxcircuit/AcxCircuitInitAssignAcxRequestPreprocessCallback
dev_langs:
 - c++
---

## -description

The AcxCircuitInitAssignAcxRequestPreprocessCallback function initializes defined AssignAcxRequest Preprocess callbacks.

## -parameters

### -param CircuitInit

The ACXCIRCUIT_INIT structure that defines the circuit initialization. ACXCIRCUIT_INIT is an opaque object used for circuit initialization. Use [AcxCircuitInitAllocate](nf-acxcircuit-acxcircuitinitallocate.md) to initialize the ACXCIRCUIT_INIT structure.

### -param EvtObjectAcxRequestPreprocess

A pointer to a [EVT_ACX_OBJECT_PREPROCESS_REQUEST](/windows-hardware/drivers/ddi/acxrequest/nc-acxrequest-evt_acx_object_preprocess_request.md) callback. 

### -param DriverContext

The driver context defined by the ACXCONTEXT object.  For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param RequestType

An [ACX_REQUEST_TYPE enum](/windows-hardware/drivers/ddi/acxrequest/ne-acxrequest-acx_request_type) that defines different request types, such as AcxRequestTypeAny or AcxRequestTypeEvent. 

### -param Set

Optional GUID to identify the associated (TBD - what type of?) Set.

### -param Id

TBD - An ID value that TBD

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
// Render callbacks.

EVT_ACX_OBJECT_PREPROCESS_REQUEST   CodecR_EvtCircuitRequestPreprocess;


    //
    // Add circuit type.
    //
    AcxCircuitInitSetCircuitType(circuitInit, AcxCircuitTypeRender);

    //
    // Assign the circuit's pnp-power callbacks.
    //
    ACX_CIRCUIT_PNPPOWER_CALLBACKS_INIT(&powerCallbacks);
    powerCallbacks.EvtAcxCircuitPowerUp = CodecR_EvtCircuitPowerUp;
    powerCallbacks.EvtAcxCircuitPowerDown = CodecR_EvtCircuitPowerDown;
    AcxCircuitInitSetAcxCircuitPnpPowerCallbacks(circuitInit, &powerCallbacks);


    //
    // Set circuit-callbacks.
    //
    status = AcxCircuitInitAssignAcxRequestPreprocessCallback(
                                            circuitInit, 
                                            CodecR_EvtCircuitRequestPreprocess,
                                            (ACXCONTEXT)AcxRequestTypeAny, // dbg only
                                            AcxRequestTypeAny,
                                            NULL, 
                                            AcxItemIdNone);
```

## -see-also

- [acxcircuit.h header](index.md)

TBD - Please review this topic