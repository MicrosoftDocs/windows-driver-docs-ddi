---
UID: NS:acxcircuit._ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT
tech.root: audio
title: ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT
ms.date: 09/30/2021
targetos: Windows
description: The ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT structure is used to remove ACX circuit factory circuits.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT, *PACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxcircuit.h
api_name:
 - _ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT
 - PACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT
 - ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT
f1_keywords:
 - _ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT
 - acxcircuit/_ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT
 - PACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT
 - acxcircuit/PACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT
 - ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT
 - acxcircuit/ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT
dev_langs:
 - c++
---

## -description

The **ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT** structure is used to remove ACX circuit factory circuits.

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field Flags

Bitwise OR of [ACX_FACTORY_CIRCUIT_REMOVE_CIRCUIT_FLAGS](ne-acxcircuit-acx_factory_circuit_remove_circuit_flags.md)

### -field CircuitUniqueId

A GUID that is used to uniquely identify the circuit.

## -remarks

ACX Manager initializes and sends this structure to an ACXFACTORYCIRCUIT when an existing ACXCIRCUIT object must be removed.

Drivers receive this structure in their ACXFACTORYCIRCUIT's callback as passing parameter.

For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### Example

Example pending.

```cpp

```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)
