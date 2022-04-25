---
UID: NF:acxcircuit.AcxCircuitGetWdfDevice
tech.root: audio
title: AcxCircuitGetWdfDevice
ms.date: 08/16/2021
targetos: Windows
description: Given an existing Acx Circuit object, the AcxCircuitGetWdfDevice returns the associated WDFDEVICE object.
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
 - AcxCircuitGetWdfDevice
f1_keywords:
 - AcxCircuitGetWdfDevice
 - acxcircuit/AcxCircuitGetWdfDevice
dev_langs:
 - c++
---

## -description

Given an existing Acx Circuit object, the AcxCircuitGetWdfDevice returns the associated (TBD - parent?) WDFDEVICE object.

## -parameters

### -param Circuit

TBD - An existing ACXCIRCUIT circuit object.  For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that is associated with (TBD- is also the parent of?) the ACX circuit object.
  
## -remarks

### Example

Example usage is shown below.

```cpp
    ACXCIRCUIT                      circuit = (ACXCIRCUIT)DriverContext;
    WDFDEVICE                       device = nullptr;

    device = AcxCircuitGetWdfDevice(circuit);
```

## -see-also

- [acxcircuit.h header](index.md)

TBD - Please review this topic