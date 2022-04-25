---
UID: NF:acxtargets.AcxTargetCircuitGetTargetPin
tech.root: audio
title: AcxTargetCircuitGetTargetPin
ms.date: 02/02/2022
targetos: Windows
description: The AcxTargetCircuitGetTargetPin function, given a valid pin index value, will return an *ACXTARGETPIN* ACX Object that is associated with the specified circuit.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxtargets.h
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
 - acxtargets.h
api_name:
 - AcxTargetCircuitGetTargetPin
f1_keywords:
 - AcxTargetCircuitGetTargetPin
 - acxtargets/AcxTargetCircuitGetTargetPin
dev_langs:
 - c++
---

## -description

The **AcxTargetCircuitGetTargetPin** function, given a valid pin index value, will return an *ACXTARGETPIN* ACX Object that is associated with the specified circuit.

## -parameters

### -param TargetCircuit

A pointer to a location of an existing ACXTARGETCIRCUIT Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param PinIndex

A valid pin index value.

## -returns

Returns a ACXTARGETELEMENT ACX Object that is associated with the specified circuit.

## -remarks

Framework request objects represent I/O requests that the I/O manager has sent to a driver. Framework-based drivers process each I/O request by calling framework request object methods. For more information, see [Framework Request Objects](/windows-hardware/drivers/wdf/framework-request-objects).

### Example

```cpp
    PDSP_CIRCUIT_CONTEXT circuitCtx;
    ACX_REQUEST_PARAMETERS  params;

    circuitCtx = GetDspCircuitContext(Circuit);    

    for (ULONG pinIndex = 0; pinIndex < AcxTargetCircuitGetPinsCount(TargetCircuit); ++pinIndex)
    {
        ACXTARGETPIN targetPin = AcxTargetCircuitGetTargetPin(TargetCircuit, pinIndex);
        ULONG targetPinFlow = 0;
        ACX_REQUEST_PARAMETERS_INIT_PROPERTY(&params,
                                             KSPROPSETID_Pin,
                                             KSPROPERTY_PIN_DATAFLOW,
                                             AcxPropertyVerbGet,
                                             AcxItemTypePin,
                                             AcxTargetPinGetId(targetPin),
                                             nullptr, 0,
                                             &targetPinFlow,
                                             sizeof(targetPinFlow));
...

    }
```

## -see-also

- [acxtargets.h header](index.md)
 
TBD - Please review this topic