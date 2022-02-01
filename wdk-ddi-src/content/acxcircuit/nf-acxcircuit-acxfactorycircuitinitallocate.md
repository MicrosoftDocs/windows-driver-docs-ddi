---
UID: NF:acxcircuit.AcxFactoryCircuitInitAllocate
tech.root: audio
title: AcxFactoryCircuitInitAllocate
ms.date: 01/31/2022
targetos: Windows
description: The AcxFactoryCircuitInitAllocate function is used to initialize the opaque ACXFACTORYCIRCUIT_INIT structure that is used by the AcxCircuitCreate function. 
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
 - AcxFactoryCircuitInitAllocate
f1_keywords:
 - AcxFactoryCircuitInitAllocate
 - acxcircuit/AcxFactoryCircuitInitAllocate
dev_langs:
 - c++
---

## -description

The AcxFactoryCircuitInitAllocate function is used to initialize the opaque ACXFACTORYCIRCUIT_INIT structure that is used by the [AcxCircuitCreate function](nf-acxcircuit-acxcircuitcreate.md). 

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that is associated with the ACX circuit.

## -returns

A pointer to an initialized ACXFACTORYCIRCUIT_INIT structure. This is an opaque structure that is accessed using APIs.

## -remarks

### Example

Example usage is shown below.

```cpp
    //
    // Get a FactoryCircuitInit structure.
    //
    PACXFACTORYCIRCUIT_INIT factoryInit = NULL;
    factoryInit = AcxFactoryCircuitInitAllocate(Device);

```

## -see-also

[acxcircuit.h header](index.md)

