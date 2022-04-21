---
UID: NF:acxcircuit.AcxFactoryCircuitInitAssignComponentUri
tech.root: audio
title: AcxFactoryCircuitInitAssignComponentUri
ms.date: 08/23/2021
targetos: Windows
description: The AcxFactoryCircuitInitAssignComponentUri function assigns a ComponentUri that will be used for the circuit initialization.
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
 - AcxFactoryCircuitInitAssignComponentUri
f1_keywords:
 - AcxFactoryCircuitInitAssignComponentUri
 - acxcircuit/AcxFactoryCircuitInitAssignComponentUri
dev_langs:
 - c++
---

## -description

The AcxFactoryCircuitInitAssignComponentUri function assigns a ComponentUri that will be used for the circuit initialization.

## -parameters

### -param FactoryInit

An ACXFACTORYCIRCUIT_INIT structure that is used for circuit factory initialization. This is an opaque structure that is used to store ACX Circuit factory initialization information and associate the factory with a WDF device.
Use the [AcxFactoryCircuitInitAllocate function](nf-acxcircuit-acxfactorycircuitinitallocate.md) to initialize the ACXFACTORYCIRCUIT_INIT structure.

### -param ComponentUri

TBD - A unicode string describes the component that is used as a URI to TBD TBD TBD.

TBD - The unicode string may match an ACPI value - TBD - DISCO value.

`DECLARE_CONST_UNICODE_STRING(dspFactoryUri, L"acpi:obj-path:\\_SB.PC00.HDAS");`

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

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

## -see-also

- [acxcircuit.h header](index.md)

TBD - Please review this topic