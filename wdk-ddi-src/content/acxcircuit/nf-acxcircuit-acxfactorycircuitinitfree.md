---
UID: NF:acxcircuit.AcxFactoryCircuitInitFree
tech.root: audio
title: AcxFactoryCircuitInitFree
ms.date: 12/14/2022
targetos: Windows
description: The AcxFactoryCircuitInitFree function deletes the factory circuit initialization object.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
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
 - acxcircuit.h
api_name:
 - AcxFactoryCircuitInitFree
f1_keywords:
 - AcxFactoryCircuitInitFree
 - acxcircuit/AcxFactoryCircuitInitFree
dev_langs:
 - c++
---

## -description

The **AcxFactoryCircuitInitFree** function deletes the factory circuit initialization object.

## -parameters

### -param FactoryInit

An ACXFACTORYCIRCUIT_INIT structure that is used for circuit factory initialization. This is an opaque structure that is used to store ACX Circuit factory initialization information and associate the factory with a WDF device.

Use the [AcxFactoryCircuitInitAllocate function](nf-acxcircuit-acxfactorycircuitinitallocate.md) to initialize the ACXFACTORYCIRCUIT_INIT structure.

## -remarks

This function does not return a value.

The driver is responsible for deleting the ACXFACTORYCIRCUIT_INIT object using this DDI if the AcxFactoryCircuitCreate is not invoked or returns an error.

### Example

Example usage is shown below.

```cpp
// Get a FactoryCircuitInit structure

  ctrlInit = AcxFactoryCircuitInitAllocate(Device);

...

// Example exit routine that shows freeing an example init structure

exit:
    if (!NT_SUCCESS(status))
    {
        if (ctrlInit)
        {
            AcxFactoryCircuitInitFree(ctrlInit);
            ctrlInit = nullptr;
        }
    }
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)
