---
UID: NF:acxcircuit.AcxFactoryCircuitInitSetComponentId
tech.root: audio
title: AcxFactoryCircuitInitSetComponentId
ms.date: 02/02/2022
targetos: Windows
description: The AcxFactoryCircuitInitSetComponentId function is used to set the component ID during the ACX circuit factory initialization process.
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
 - AcxFactoryCircuitInitSetComponentId
f1_keywords:
 - AcxFactoryCircuitInitSetComponentId
 - acxcircuit/AcxFactoryCircuitInitSetComponentId
dev_langs:
 - c++
---

## -description

The AcxFactoryCircuitInitSetComponentId function is used to set the component ID during the ACX circuit factory initialization process.

## -parameters

### -param FactoryInit

An ACXFACTORYCIRCUIT_INIT structure that is used for circuit factory initialization. This is an opaque structure that is used to store ACX Circuit factory initialization information and associate the factory with a WDF device.
Use the [AcxFactoryCircuitInitAllocate function](nf-acxcircuit-acxfactorycircuitinitallocate.md) to initialize the ACXFACTORYCIRCUIT_INIT structure.

### -param ComponentId

A defined GUID that serves as the component ID for the Circuit. For example:

```cpp
DEFINE_GUID(COMPONENT_GUID, 
0xf55ba68e, 0x4384, 0x4030, 0x97, 0x19, 0xec, 0xa4, 0xbe, 0x27, 0x6c, 0xc8);
```

## -remarks

### Example

Example usage is shown below.

TBD - Is it OK to show the SDC AXU FACTORY GUID? Perhaps show all zeroes or some other GUID value for the code example?

```cpp
DEFINE_GUID(SDCAXU_FACTORY_GUID, 
0x63434534, 0xBD84, 0x8DFE, 0x7A, 0xAA, 0xFF, 0x84, 0xD8, 0x23, 0xAB, 0xBD);

    //
    // Get a FactoryCircuitInit structure.
    //
    factoryInit = AcxFactoryCircuitInitAllocate(Device);

    //
    // Add factory identifiers.
    //
    AcxFactoryCircuitInitSetComponentId(factoryInit, &SDCAXU_FACTORY_GUID);
```

## -see-also

[acxcircuit.h header](index.md)

TBD - Please review this topic