---
UID: NF:acxcircuit.AcxCircuitInitFree
tech.root: audio
title: AcxCircuitInitFree
ms.date: 07/28/2022
targetos: Windows
description: The AcxCircuitInitFree function deletes the circuit initialization object.
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
 - AcxCircuitInitFree
f1_keywords:
 - AcxCircuitInitFree
 - acxcircuit/AcxCircuitInitFree
dev_langs:
 - c++
---

## -description

The **AcxCircuitInitFree** function deletes the circuit initialization object.

## -parameters

### -param CircuitInit

The ACXCIRCUIT_INIT structure that defines the circuit initialization. ACXCIRCUIT_INIT is an opaque object used for circuit initialization. Use [AcxCircuitInitAllocate](nf-acxcircuit-acxcircuitinitallocate.md) to initialize the ACXCIRCUIT_INIT structure.

## -remarks

This function does not return a value.

The driver is responsible for deleting the ACXCIRCUIT_INIT object using this DDI if the AcxCircuitCreate is not invoked or returns an error.

### Example

Example usage is shown below.

```cpp

    //
    // Get a CircuitInit structure.
    //
    PACXCIRCUIT_INIT circuitInit = NULL;
    circuitInit = AcxCircuitInitAllocate(Device);

// Later in the code on an exit close down process...

exit:
    if (!NT_SUCCESS(status))
    {
        if (circuitInit)
        {
            AcxCircuitInitFree(circuitInit);
        }
    }

```

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)

