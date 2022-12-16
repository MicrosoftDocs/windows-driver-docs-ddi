---
UID: NF:acxtargets.AcxTargetCircuitGetTargetPin
tech.root: audio
title: AcxTargetCircuitGetTargetPin
ms.date: 12/16/2022
targetos: Windows
description: The AcxTargetCircuitGetTargetPin function, given a valid pin index value, will return the associated ACXTARGETPIN object.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxtargets.h
req.idl: 
req.include-header: 
req.irql: <= DISPATCH_LEVEL
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

The **AcxTargetCircuitGetTargetPin** function, given a valid pin index value, will return the associated *ACXTARGETPIN* object.

## -parameters

### -param TargetCircuit

An ACXTARGETCIRCUIT handle. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param PinIndex

A valid pin index value.

## -returns

Returns a ACXTARGETELEMENT ACX Object that is associated with the specified circuit.

## -remarks

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

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxtargets.h header](index.md)
