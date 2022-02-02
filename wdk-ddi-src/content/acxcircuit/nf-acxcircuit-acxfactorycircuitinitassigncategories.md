---
UID: NF:acxcircuit.AcxFactoryCircuitInitAssignCategories
tech.root: audio
title: AcxFactoryCircuitInitAssignCategories
ms.date: 08/18/2021
targetos: Windows
description: The AcxFactoryCircuitInitAssignCategories function assigns an array of GUIDS that are KSCATERGORY entries, that are used during Acx Circuit Factory initialization. 
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
 - AcxFactoryCircuitInitAssignCategories
f1_keywords:
 - AcxFactoryCircuitInitAssignCategories
 - acxcircuit/AcxFactoryCircuitInitAssignCategories
dev_langs:
 - c++
---

## -description

The AcxFactoryCircuitInitAssignCategories function assigns an array of GUIDS that are the desired set of KSCATERGORY entries, that are used during Acx Circuit Factory initialization. 

## -parameters

### -param FactoryInit

An ACXFACTORYCIRCUIT_INIT structure that is used for circuit factory initialization. This is an opaque structure that is used to store ACX Circuit factory initialization information and associate the factory with a WDF device.
Use the [AcxFactoryCircuitInitAllocate function](nf-acxcircuit-acxfactorycircuitinitallocate.md) to initialize the ACXFACTORYCIRCUIT_INIT structure.

### -param Categories

TBD - An array that contains GUIDS of the desired set of KSCATERGORY entries, for example `KSCATEGORY_AUDIO`. For more information about the KSCATERGORY entries, see [Installing Device Interfaces for an Audio Adapter](/windows-hardware/drivers/audio/installing-device-interfaces-for-an-audio-adapter).

### -param CategoriesCount

TBD - The number of categories that will be added to the circuit. This is a TBD zero / one based count.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
    ACXFACTORYCIRCUIT                               factory;
    PACXFACTORYCIRCUIT_INIT                         factoryInit = NULL;
    SDCAXU_FACTORYCIRCUIT_CONTEXT *                 factoryCtx;
    ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS         operationCallbacks;

    //
    // Get a FactoryCircuitInit structure.
    //
    factoryInit = AcxFactoryCircuitInitAllocate(Device);

    //
    // Add factory identifiers.
    //
    AcxFactoryCircuitInitSetComponentId(factoryInit, &SDCAXU_FACTORY_GUID);
    AcxFactoryCircuitInitAssignCategories(factoryInit, &SDCAXU_FACTORY_CATEGORY, 1);
```

## -see-also

[acxcircuit.h header](index.md)

