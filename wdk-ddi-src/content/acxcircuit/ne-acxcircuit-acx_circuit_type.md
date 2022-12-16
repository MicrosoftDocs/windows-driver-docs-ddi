---
UID: NE:acxcircuit._ACX_CIRCUIT_TYPE
tech.root: audio
title: ACX_CIRCUIT_TYPE
ms.date: 06/16/2022
targetos: Windows
description: The ACX_CIRCUIT_TYPE enumeration defines the types of ACXCIRCUITs.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: acxcircuit.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxcircuit.h
api_name:
 - _ACX_CIRCUIT_TYPE
 - PACX_CIRCUIT_TYPE
 - ACX_CIRCUIT_TYPE
f1_keywords:
 - _ACX_CIRCUIT_TYPE
 - acxcircuit/_ACX_CIRCUIT_TYPE
 - PACX_CIRCUIT_TYPE
 - acxcircuit/PACX_CIRCUIT_TYPE
 - ACX_CIRCUIT_TYPE
 - acxcircuit/ACX_CIRCUIT_TYPE
dev_langs:
 - c++
---

## -description

The **ACX_CIRCUIT_TYPE** enumeration defines the types of ACXCIRCUITs.

## -enum-fields

### -field AcxCircuitTypeOther

The circuit type is other.

### -field AcxCircuitTypeRender

The circuit type is render.

### -field AcxCircuitTypeCapture

The circuit type is capture.

### -field AcxCircuitTypeMaximum

For internal validation, do not use.

## -remarks

### Example

Example usage is shown below.

```cpp
   ACX_CIRCUIT_TYPE                circuitType     = AcxCircuitTypeRender;
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header\]\(index.md\)
