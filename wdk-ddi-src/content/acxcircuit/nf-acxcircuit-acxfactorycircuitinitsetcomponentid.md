---
UID: NF:acxcircuit.AcxFactoryCircuitInitSetComponentId
tech.root: audio
title: AcxFactoryCircuitInitSetComponentId
ms.date: 
targetos: Windows
description: 
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

## -parameters

### -param FactoryInit

TBD - An ACXFACTORYCIRCUIT_INIT structure that is used for circuit factory initialization. This is an opaque structure that is used to store ACX Circuit factory initialization information and associate the factory with a WDF device.
Use the [AcxFactoryCircuitInitAllocate function](nf-acxcircuit-acxfactorycircuitinitallocate.md) to initialize the ACXFACTORYCIRCUIT_INIT structure.

### -param ComponentId

## -remarks

### Example

Example usage is shown below.

```cpp

```

## -see-also

[acxcircuit.h header](index.md)

