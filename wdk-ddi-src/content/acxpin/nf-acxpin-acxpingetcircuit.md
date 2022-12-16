---
UID: NF:acxpin.AcxPinGetCircuit
tech.root: audio
title: AcxPinGetCircuit
ms.date: 04/11/2022
targetos: Windows
description: The AcxPinGetCircuit function returns the circuit to which the pin is connected.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxpin.h
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
 - LibDef
api_location:
 - acxpin.h
api_name:
 - AcxPinGetCircuit
f1_keywords:
 - AcxPinGetCircuit
 - acxpin/AcxPinGetCircuit
dev_langs:
 - c++
---

## -description

The **AcxPinGetCircuit** function returns the circuit to which the specified pin is connected.

## -parameters

### -param AcxPin [in]

The pin for which to return the connected circuit.

## -returns

Returns the [ACXCIRCUIT](../acxcircuit/index.md) object representing the circuit to which the *AcxPin* is connected.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACXCIRCUIT](../acxcircuit/index.md)
- [acxpin.h header\]\(index.md\)
