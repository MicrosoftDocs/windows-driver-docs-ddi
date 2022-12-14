---
UID: NF:acxcircuit.ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS_INIT
tech.root: audio
title: ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS_INIT
ms.date: 08/13/2021
targetos: Windows
description: The ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS_INIT function initializes a ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS structure.
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
 - ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS_INIT
f1_keywords:
 - ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS_INIT
 - acxcircuit/ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS_INIT
dev_langs:
 - c++
---

## -description

The **ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS_INIT** function initializes a 
[ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS](ns-acxcircuit-acx_factory_circuit_pnppower_callbacks.md) structure. No inputs are used with this function.

## -parameters

### -param PnpPowerCallbacks

A pointer to an initialized [ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS structure](ns-acxcircuit-acx_factory_circuit_pnppower_callbacks.md).

## -remarks

ACX doesn't support the PNP callbacks for a circuit factory object.

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)

