---
UID: NF:acxcircuit.AcxFactoryCircuitInitAssignComponentUri
tech.root: audio
title: AcxFactoryCircuitInitAssignComponentUri
ms.date: 12/14/2022
targetos: Windows
description: The AcxFactoryCircuitInitAssignComponentUri function assigns an URI string as identifier for the ACXFACTORYCIRCUIT.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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
 - AcxFactoryCircuitInitAssignComponentUri
f1_keywords:
 - AcxFactoryCircuitInitAssignComponentUri
 - acxcircuit/AcxFactoryCircuitInitAssignComponentUri
dev_langs:
 - c++
---

## -description

The AcxFactoryCircuitInitAssignComponentUri function assigns an URI string as identifier for the ACXFACTORYCIRCUIT.

## -parameters

### -param FactoryInit

An ACXFACTORYCIRCUIT_INIT structure that is used for circuit factory initialization. This is an opaque structure that is used to store ACX Circuit factory initialization information and associate the factory with a WDF device.

Use the [AcxFactoryCircuitInitAllocate function](nf-acxcircuit-acxfactorycircuitinitallocate.md) to initialize the ACXFACTORYCIRCUIT_INIT structure.

### -param ComponentUri

A unicode string that describes the component.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

The driver must initialize the circuit factory's identity by setting the its URI and/or its ID (AcxCircuitInitSetComponentId).

### Example

Example usage is shown below.

```cpp
    DECLARE_CONST_UNICODE_STRING(dspFactoryName, L"DspFactoryCircuit");
    DECLARE_CONST_UNICODE_STRING(dspFactoryUri, L"URI_Goes_Here");

    //
    // Get a FactoryCircuitInit structure.
    //
    PACXFACTORYCIRCUIT_INIT factoryInit = NULL;
    factoryInit = AcxFactoryCircuitInitAllocate(Device);

    //
    // Add factory identifiers.
    //
    status = cxFactoryCircuitInitAssignComponentUri(factoryInit, &dspFactoryUri);
    status = AcxFactoryCircuitInitAssignName(factoryInit, &dspFactoryName);
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)
