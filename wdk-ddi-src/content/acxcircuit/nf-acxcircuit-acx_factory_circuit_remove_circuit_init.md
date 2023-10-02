---
UID: NF:acxcircuit.ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT_INIT
tech.root: audio
title: ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT_INIT
ms.date: 07/28/2022
targetos: Windows
description: The ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT_INIT function initializes a ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT structure.
prerelease: false
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
 - ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT_INIT
f1_keywords:
 - ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT_INIT
 - acxcircuit/ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT_INIT
dev_langs:
 - c++
---

## -description

The **ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT_INIT** function initializes a [ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT](ns-acxcircuit-acx_factory_circuit_remove_circuit.md) structure. No inputs are used with this function.

## -parameters

### -param Parameters

A pointer to a [ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT](ns-acxcircuit-acx_factory_circuit_remove_circuit.md) structure that will be initialized.

## -remarks

NOTE: internal only, do not use.

### Example

Example usage is shown below.

```cpp
    ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT  remParams;

    m_CircuitRequested = false;

    ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT_INIT(&remParams);
    remParams.CircuitUniqueId = m_CircuitUniqueId;
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)
