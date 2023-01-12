---
UID: NF:acxcircuit.AcxCircuitGetSymbolicLinkName
tech.root: audio
title: AcxCircuitGetSymbolicLinkName
ms.date: 12/14/2022
targetos: Windows
description: The AcxCircuitGetSymbolicLinkName function retrieves the symbolic link name for the specified circuit object.
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
 - AcxCircuitGetSymbolicLinkName
f1_keywords:
 - AcxCircuitGetSymbolicLinkName
 - acxcircuit/AcxCircuitGetSymbolicLinkName
dev_langs:
 - c++
helpviewer_keywords:
 - AcxCircuitGetSymbolicLinkName
---

## -description

The **AcxCircuitGetSymbolicLinkName** function retrieves the symbolic link name for the specified circuit object.

## -parameters

### -param Circuit [in]

The circuit object for which to get the symbolic link name.

## -returns

Returns a string containing the symbolic link name for the object specified by the *Circuit* parameter.

## -remarks

The symbolic link is valid:

1. After the driver adds the circuit to the device, for single-circuit endpoints.
1. When the ACX manager invokes ACX circuit initialization, for multi-circuit endpoints.

### Example

Example usage is shown below.

```cpp
...
    _In_ ACXCIRCUIT Circuit,
...

    WDFSTRING wdfLink = AcxCircuitGetSymbolicLinkName(Circuit);
```

### ACX requirements

**Minimum ACX version:** 1.1

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)
