---
UID: NF:acxcircuit.AcxCircuitInitAssignCategories
tech.root: audio
title: AcxCircuitInitAssignCategories
ms.date: 08/17/2021
targetos: Windows
description: The AcxCircuitInitAssignCategories function assigns a set of KSCATERGORY entries that will be used for the circuit initialization.
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
 - AcxCircuitInitAssignCategories
f1_keywords:
 - AcxCircuitInitAssignCategories
 - acxcircuit/AcxCircuitInitAssignCategories
dev_langs:
 - c++
---

## -description

The AcxCircuitInitAssignCategories function assigns a set of KSCATERGORY entries that will be used for the circuit initialization.

## -parameters

### -param CircuitInit

TBD- The ACXCIRCUIT_INIT structure that defines the circuit initialization. ACXCIRCUIT_INIT is an opaque object used for circuit initialization. Use [AcxCircuitInitAllocate](nf-acxcircuit-acxcircuitinitallocate.md) to initialize the ACXCIRCUIT_INIT structure.

### -param Categories

TBD - An array that contains GUIDS of the desired set of KSCATERGORY entries, for example `KSCATEGORY_AUDIO`. For more information about the KSCATERGORY entries, see [Installing Device Interfaces for an Audio Adapter](/windows-hardware/drivers/audio/installing-device-interfaces-for-an-audio-adapter).


### -param CategoriesCount

TBD - The number of categories that will be added to the circuit. This is a TBD zero / one based count.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

TBD - Should we create a config structure example?

```cpp

    GUID                            captureCategories[] =
    {
        STATICGUIDOF(KSCATEGORY_ACXCIRCUIT_DUP),
        GUID_NULL,    
        STATICGUIDOF(KSCATEGORY_AUDIO),
        STATICGUIDOF(KSCATEGORY_CAPTURE), 
        STATICGUIDOF(KSCATEGORY_REALTIME),
        STATICGUIDOF(KSCATEGORY_TOPOLOGY),
    };

    //
    // Add circuit identifiers.
    //
    AcxCircuitInitSetComponentId(CircuitInit, &COMPONENT_GUID);

    AcxCircuitInitAssignName(CircuitInit, &circuitName);

   // TODO: this is an overly simple example should have its own field in config.
    captureCategories[1] = Config->CircuitTagId;
    status = AcxCircuitInitAssignCategories(CircuitInit, captureCategories, SIZEOF_ARRAY(captureCategories));
```

## -see-also

[acxcircuit.h header](index.md)

