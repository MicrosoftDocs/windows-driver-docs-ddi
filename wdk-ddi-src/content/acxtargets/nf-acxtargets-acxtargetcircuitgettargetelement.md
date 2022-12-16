---
UID: NF:acxtargets.AcxTargetCircuitGetTargetElement
tech.root: audio
title: AcxTargetCircuitGetTargetElement
ms.date: 12/16/2022
targetos: Windows
description: The AcxTargetCircuitGetTargetElement function, given a valid element index value, will return the associated ACXTARGETELEMENT object.
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
 - AcxTargetCircuitGetTargetElement
f1_keywords:
 - AcxTargetCircuitGetTargetElement
 - acxtargets/AcxTargetCircuitGetTargetElement
dev_langs:
 - c++
---

## -description

The **AcxTargetCircuitGetTargetElement** function, given a valid element index value, will return the associated ACXTARGETELEMENT object.

## -parameters

### -param TargetCircuit

An ACXTARGETCIRCUIT handle. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ElementIndex

A valid element index value.

## -returns

Returns a ACXTARGETELEMENT ACX Object that is associated with the specified circuit.

## -remarks

### Example

```cpp
    // Search the target circuit for a volume element.
    // This sample code doesn't support downstream audioengine elements.
    // 
    for (ULONG elementIndex = 0; elementIndex < AcxTargetCircuitGetElementsCount(TargetCircuit); ++elementIndex)
    {
        ACXTARGETELEMENT targetElement = AcxTargetCircuitGetTargetElement(TargetCircuit, elementIndex);
        GUID elementType = AcxTargetElementGetType(targetElement);

        if (IsEqualGUID(elementType, KSNODETYPE_VOLUME) &&
            circuitCtx->TargetVolumeHandler == nullptr)
        {
            // Found Volume
            circuitCtx->TargetVolumeHandler = targetElement;
        }
    }
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxtargets.h header](index.md)
