---
UID: NF:acxcircuit.AcxCircuitInitAllocate
tech.root: audio
title: AcxCircuitInitAllocate
ms.date: 08/16/2021
targetos: Windows
description: The AcxCircuitInitAllocate function is used to initialize the opaque ACXCIRCUIT_INIT structure that is used by the AcxCircuitCreate function. 
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
 - AcxCircuitInitAllocate
f1_keywords:
 - AcxCircuitInitAllocate
 - acxcircuit/AcxCircuitInitAllocate
dev_langs:
 - c++
---

## -description

The **AcxCircuitInitAllocate** function is used to initialize the opaque ACXCIRCUIT_INIT structure that is used by the [AcxCircuitCreate function](nf-acxcircuit-acxcircuitcreate.md).

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that is associated with the ACX circuit.

## -returns

## -remarks

The driver is responsable for deleting the ACXCIRCUIT_INIT object using AcxCircuitInitFree if the AcxCircuitCreate is not invoked or returns an error.

### Example

Example usage is shown below.

```cpp
    PACXCIRCUIT_INIT    circuitInit = NULL;

    circuitInit = AcxCircuitInitAllocate(Device);
```

## -see-also

- [acxcircuit.h header](index.md)

READY2GO
