---
UID: NF:acxcircuit.AcxFactoryCircuitInitSetComponentId
tech.root: audio
title: AcxFactoryCircuitInitSetComponentId
ms.date: 12/14/2022
targetos: Windows
description: The AcxFactoryCircuitInitSetComponentId function sets the component ID for the ACXFACTORYCIRCUIT.
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
 - AcxFactoryCircuitInitSetComponentId
f1_keywords:
 - AcxFactoryCircuitInitSetComponentId
 - acxcircuit/AcxFactoryCircuitInitSetComponentId
dev_langs:
 - c++
---

## -description

The **AcxFactoryCircuitInitSetComponentId** function sets the component ID for the ACXFACTORYCIRCUIT.

## -parameters

### -param FactoryInit

An ACXFACTORYCIRCUIT_INIT structure that is used for circuit factory initialization. This is an opaque structure that is used to store ACX Circuit factory initialization information and associate the factory with a WDF device.

Use the [AcxFactoryCircuitInitAllocate function](nf-acxcircuit-acxfactorycircuitinitallocate.md) to initialize the ACXFACTORYCIRCUIT_INIT structure.

### -param ComponentId

A defined GUID that serves as the component ID for the circuit factory.

## -remarks

The driver must initialize the circuit factory's identity by setting the its URI (AcxFactoryCircuitInitAssignComponentUri) and/or its ID (this DDI).

### Example

Example usage is shown below.

```cpp
DEFINE_GUID(SDCAXU_FACTORY_GUID, 
0xa8215305, 0xe7db, 0x49eb, 0x96, 0x49, 0x84, 0x34, 0x55, 0xe2, 0xe0, 0xd1);
    //
    // Get a FactoryCircuitInit structure.
    //
    factoryInit = AcxFactoryCircuitInitAllocate(Device);

    //
    // Add factory identifiers.
    //
    AcxFactoryCircuitInitSetComponentId(factoryInit, &SDCAXU_FACTORY_GUID);
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)
