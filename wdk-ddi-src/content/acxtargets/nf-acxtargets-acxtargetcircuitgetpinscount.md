---
UID: NF:acxtargets.AcxTargetCircuitGetPinsCount
tech.root: audio
title: AcxTargetCircuitGetPinsCount
ms.date: 04/22/2022
targetos: Windows
description: The AcxTargetCircuitGetPinsCount function returns the count of ACX pins on the remote target.
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
 - AcxTargetCircuitGetPinsCount
f1_keywords:
 - AcxTargetCircuitGetPinsCount
 - acxtargets/AcxTargetCircuitGetPinsCount
dev_langs:
 - c++
---

## -description

The **AcxTargetCircuitGetPinsCount** function returns the count of ACX pins on the remote target.

## -parameters

### -param TargetCircuit

An AXTARGETCIRCUIT handle. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns the number of ACX pins on the remote target.

## -remarks

### Example

```cpp
    ULONG pinCount;

    pinCount = AcxTargetCircuitGetPinsCount(targetCircuit);
```

## -see-also

- [acxtargets.h header](index.md)
 
READY2GO
