---
UID: NS:acxcircuit._ACX_CIRCUIT_PNPPOWER_CALLBACKS
tech.root: audio
title: ACX_CIRCUIT_PNPPOWER_CALLBACKS
ms.date: 08/12/2021
targetos: Windows
description: The ACX_CIRCUIT_PNPPOWER_CALLBACKS structure contains pointers to an ACXCIRCUIT's Plug and Play and power event callback functions.
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
req.typenames: ACX_CIRCUIT_PNPPOWER_CALLBACKS, *PACX_CIRCUIT_PNPPOWER_CALLBACKS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxcircuit.h
api_name:
 - _ACX_CIRCUIT_PNPPOWER_CALLBACKS
 - PACX_CIRCUIT_PNPPOWER_CALLBACKS
 - ACX_CIRCUIT_PNPPOWER_CALLBACKS
f1_keywords:
 - _ACX_CIRCUIT_PNPPOWER_CALLBACKS
 - acxcircuit/_ACX_CIRCUIT_PNPPOWER_CALLBACKS
 - PACX_CIRCUIT_PNPPOWER_CALLBACKS
 - acxcircuit/PACX_CIRCUIT_PNPPOWER_CALLBACKS
 - ACX_CIRCUIT_PNPPOWER_CALLBACKS
 - acxcircuit/ACX_CIRCUIT_PNPPOWER_CALLBACKS
dev_langs:
 - c++
---

## -description

The **ACX_CIRCUIT_PNPPOWER_CALLBACKS** structure contains pointers to an ACXCIRCUIT's Plug and Play and power event callback.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field EvtAcxCircuitPrepareHardware

A pointer to the driver's [ACX_CIRCUIT_PREPARE_HARDWARE callback](nc-acxcircuit-evt_acx_factory_circuit_prepare_hardware.md) event callback function, or NULL.

### -field EvtAcxCircuitReleaseHardware

A pointer to the driver's [ACX_CIRCUIT_RELEASE_HARDWARE callback](nc-acxcircuit-evt_acx_factory_circuit_release_hardware.md) event callback function, or NULL.

### -field EvtAcxCircuitPowerUp

A pointer to the [ACX_CIRCUIT_POWER_UP callback](nc-acxcircuit-evt_acx_factory_circuit_power_up.md) event callback function, or NULL.

### -field EvtAcxCircuitPowerDown

A pointer to the [ACX_CIRCUIT_POWER_DOWN callback](nc-acxcircuit-evt_acx_factory_circuit_power_down.md) event callback function, or NULL.

## -remarks

The ACX_CIRCUIT_PNPPOWER_CALLBACKS structure is used as input to the [AcxCircuitInitSetAcxCircuitPnpPowerCallbacks method](nf-acxcircuit-acxcircuitinitsetacxcircuitpnppowercallbacks.md).

Your driver should initialize its ACX_CIRCUIT_PNPPOWER_CALLBACKS structure by calling [ACX_CIRCUIT_PNPPOWER_CALLBACKS_INIT](nf-acxcircuit-acx_circuit_pnppower_callbacks_init.md).

### Example

Example usage is shown below.

```cpp
    //
    // Assign the circuit's pnp-power callbacks.
    //
    {
        ACX_CIRCUIT_PNPPOWER_CALLBACKS  powerCallbacks;
        ACX_CIRCUIT_PNPPOWER_CALLBACKS_INIT(&powerCallbacks);
        powerCallbacks.EvtAcxCircuitPowerUp = EvtCircuitPowerUp;
        powerCallbacks.EvtAcxCircuitPowerDown = EvtCircuitPowerDown;
        AcxCircuitInitSetAcxCircuitPnpPowerCallbacks(CircuitInit, &powerCallbacks);
    }
    
    status = AcxCircuitInitAssignAcxCreateStreamCallback(CircuitInit, EvtCircuitCreateStream);
```

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

[ACX_CIRCUIT_PNPPOWER_CALLBACKS_INIT](nf-acxcircuit-acx_circuit_pnppower_callbacks_init.md)

[AcxCircuitInitSetAcxCircuitPnpPowerCallbacks method](nf-acxcircuit-acxcircuitinitsetacxcircuitpnppowercallbacks.md)

- [acxcircuit.h header](index.md)

