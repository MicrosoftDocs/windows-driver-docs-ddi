---
UID: NF:acxtargets.AcxTargetCircuitGetElementsCount
tech.root: audio
title: AcxTargetCircuitGetElementsCount
ms.date: 12/16/2022
targetos: Windows
description: The AcxTargetCircuitGetElementsCount function returns the count of ACX elements on the remote target.
prerelease: false
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
 - AcxTargetCircuitGetElementsCount
f1_keywords:
 - AcxTargetCircuitGetElementsCount
 - acxtargets/AcxTargetCircuitGetElementsCount
dev_langs:
 - c++
---

## -description

The **AcxTargetCircuitGetElementsCount** function returns the count of ACX elements on the remote target.

## -parameters

### -param TargetCircuit

An ACXTARGETCIRCUIT handle. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns the number of elements for the specified target circuit.

## -remarks

### Example

```cpp
    ULONG elementCount;

    elementCount = AcxTargetCircuitGetElementsCount(targetCircuit);
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxtargets.h header](index.md)
