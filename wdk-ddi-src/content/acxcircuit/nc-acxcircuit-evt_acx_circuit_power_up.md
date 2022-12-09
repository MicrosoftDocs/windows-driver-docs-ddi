---
UID: NC:acxcircuit.EVT_ACX_CIRCUIT_POWER_UP
tech.root: audio
title: EVT_ACX_CIRCUIT_POWER_UP
ms.date: 12/08/2022
targetos: Windows
description: The EVT_ACX_CIRCUIT_POWER_UP callback is used by the driver to add functionality in the power up path of an ACXCIRCUIT object.
prerelease: true
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
 - LibDef
api_location:
 - acxcircuit.h
api_name:
 - EVT_ACX_CIRCUIT_POWER_UP
f1_keywords:
 - EVT_ACX_CIRCUIT_POWER_UP
 - acxcircuit/EVT_ACX_CIRCUIT_POWER_UP
dev_langs:
 - c++
---

## -description

The **EVT_ACX_CIRCUIT_POWER_UP** callback is used by the driver to add functionality in the power up path of an ACXCIRCUIT object.

## -parameters

### -param Device

A WDFDEVICE object (described in  [WDF - Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) associated with the specified ACXCIRCUIT.

### -param Circuit

The ACXCIRCUIT object (described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects)) powered up.

### -param PreviousState

A WDF_POWER_DEVICE_STATE-typed enumerator that identifies the previous device power state.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).
If the driver fails this callback, the ACX framework shutdowns the associated ACXSTREAMS if any, and tags the ACXCIRCUIT as pending-delete. The ACX framework doesn't fail the underline ACX EvtDeviceD0Entry callback, this allows existing working ACXCIRCUITs from this device to be used to build working audio paths. 

## -remarks

To register an EvtCircuitPowerUp callback function, a driver must call [AcxCircuitInitSetAcxCircuitPnpPowerCallbacks](nf-acxcircuit-acxcircuitinitsetacxcircuitpnppowercallbacks.md).

If the driver has registered an EvtCircuitPowerUp callback function for a device, the framework calls the function each time the device enters its working (D0) state. A device will enter the D0 state when one of the following occurs:

- A device is enumerated (because the device was plugged in or the system was rebooted).
- The system and all of its devices return to their working states from a low-power state.
- The device returns to its working state after it entered a low-power state because it was idle (if the device supports low-power idle).
- The Plug and Play manager has redistributed the system's hardware resources among the system's devices.
- The framework calls the EvtDeviceD0Entry callback function immediately after the device enters its working (D0) state and is available to the driver, but before the device's interrupts have been enabled. The PreviousState parameter identifies the device power state that the device was in before it entered the D0 state. When the framework first calls EvtDeviceD0Entry, it provides a PreviousState value of WdfPowerDeviceD3Final.

This callback function must perform any operations that are needed to make the device fully operational.

For more information about drivers that provide this callback function, see [Supporting PnP and Power Management in Function Driver](/windows-hardware/drivers/wdf/supporting-pnp-and-power-management-in-function-drivers).

The EvtCircuitPowerUp callback function is called at IRQL = PASSIVE_LEVEL. You should not make this callback function pageable.

### Example

Example usage is shown below. This example shows starting some timer values for use in test code.

```cpp
EVT_ACX_CIRCUIT_POWER_UP            CodecR_EvtCircuitPowerUp;

NTSTATUS
CreateCircuit()
{
    ...
    ACX_CIRCUIT_PNPPOWER_CALLBACKS_INIT(&powerCallbacks);
    powerCallbacks.EvtAcxCircuitPowerUp = CodecR_EvtCircuitPowerUp;
    powerCallbacks.EvtAcxCircuitPowerDown = CodecR_EvtCircuitPowerDown;
    AcxCircuitInitSetAcxCircuitPnpPowerCallbacks(circuitInit, &powerCallbacks);
    ...
}

NTSTATUS
CodecR_EvtCircuitPowerUp (
    _In_ WDFDEVICE  Device,
    _In_ ACXCIRCUIT Circuit,
    _In_ WDF_POWER_DEVICE_STATE PreviousState
    )
{
    UNREFERENCED_PARAMETER(Device);
    UNREFERENCED_PARAMETER(PreviousState);

    CODEC_RENDER_CIRCUIT_CONTEXT *  circuitCtx;
    CODEC_MUTE_ELEMENT_CONTEXT *    muteCtx;
    CODEC_VOLUME_ELEMENT_CONTEXT *  volumeCtx;

    PAGED_CODE();

    // for testing. 
    circuitCtx = GetRenderCircuitContext(Circuit);
    ASSERT(circuitCtx);

    ASSERT(circuitCtx->MuteElement);
    muteCtx = GetCodecMuteElementContext(circuitCtx->MuteElement);
    ASSERT(muteCtx);

    ASSERT(muteCtx->Timer);
    WdfTimerStart(muteCtx->Timer, WDF_REL_TIMEOUT_IN_MS(10));

    ASSERT(circuitCtx->VolumeElement);
    volumeCtx = GetCodecVolumeElementContext(circuitCtx->VolumeElement);
    ASSERT(volumeCtx);

    ASSERT(volumeCtx->Timer);
    WdfTimerStart(volumeCtx->Timer, WDF_REL_TIMEOUT_IN_MS(1000));
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)

[Supporting PnP and Power Management in Function Driver](/windows-hardware/drivers/wdf/supporting-pnp-and-power-management-in-function-drivers)

