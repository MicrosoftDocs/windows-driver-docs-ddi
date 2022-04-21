---
UID: NF:acxcircuit.AcxFactoryCircuitInitAssignName
tech.root: audio
title: AcxFactoryCircuitInitAssignName
ms.date: 02/02/2022
targetos: Windows
description: The AcxFactoryCircuitInitAssignName function assigns a friendly (TBD?) Name that will be used for the circuit initialization.
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
 - AcxFactoryCircuitInitAssignName
f1_keywords:
 - AcxFactoryCircuitInitAssignName
 - acxcircuit/AcxFactoryCircuitInitAssignName
dev_langs:
 - c++
---

## -description

The AcxFactoryCircuitInitAssignName function assigns a friendly (TBD?) Name that will be used for the circuit initialization.

## -parameters

### -param FactoryInit

An ACXFACTORYCIRCUIT_INIT structure that is used for circuit factory initialization. This is an opaque structure that is used to store ACX Circuit factory initialization information and associate the factory with a WDF device.
Use the [AcxFactoryCircuitInitAllocate function](nf-acxcircuit-acxfactorycircuitinitallocate.md) to initialize the ACXFACTORYCIRCUIT_INIT structure.

### -param FactoryName

TBD - A unicode string describes the circuit, such as *Microphone0* or *Render* that is used as a friendly TBD name for the circuit.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
//
// Factory Name.
//
DECLARE_CONST_UNICODE_STRING(s_FactoryName, L"Render");
    
    //
    // Get a FactoryCircuitInit structure.
    //
    factoryInit = AcxFactoryCircuitInitAllocate(Device);

    //
    // Add factory identifiers.
    //
    AcxFactoryCircuitInitSetComponentId(factoryInit, &KSCATEGORY_APXCIRCUITFACTORY);
    AcxFactoryCircuitInitAssignCategories(factoryInit, &KSCATEGORY_APXCIRCUITFACTORY, 1);
    AcxFactoryCircuitInitAssignName(factoryInit, &s_FactoryName);

```

## -see-also

[acxcircuit.h header](index.md)

TBD - Please review this topic