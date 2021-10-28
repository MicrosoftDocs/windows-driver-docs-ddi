---
UID: NC:acxcircuit.EVT_ACX_CIRCUIT_POWER_DOWN
tech.root: audio
title: EVT_ACX_CIRCUIT_POWER_DOWN
ms.date: 08/23/2021
targetos: Windows
description: The EVT_ACX_CIRCUIT_POWER_DOWN callback is used by the driver to add functionality in the power down path of an ACXCIRCUIT object.
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
 - LibDef
api_location:
 - acxcircuit.h
api_name:
 - EVT_ACX_CIRCUIT_POWER_DOWN
f1_keywords:
 - EVT_ACX_CIRCUIT_POWER_DOWN
 - acxcircuit/EVT_ACX_CIRCUIT_POWER_DOWN
dev_langs:
 - c++
---

## -description

The EVT_ACX_CIRCUIT_POWER_DOWN callback is used by the driver to add functionality in the power down path of a ACXCIRCUIT object.

## -parameters

### -param Device

A WDFDEVICE object (described in  [WDF - Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) associated with the specified ACXCIRCUIT. 

### -param Circuit

The ACXCIRCUIT object (described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects)) powered down.

### -param TargetState

A WDF_POWER_DEVICE_STATE-typed enumerator that identifies the device power state that the device is about to enter.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

To register an EvtCircuitPowerDown callback function, a driver must call AcxCircuitInitSetAcxCircuitPnpPowerCallbacks.

If the driver has registered an EvtCircuitPowerDown callback function, the ACX framework calls the function each time one of the driver's devices leaves its working (D0) state. A device leaves the D0 state when one of the following occurs:

. The system and all of its devices are about to leave their working states and enter a low-power state.
. The device is about to enter a low-power state because it is idle, if the device supports low-power idle.
. The Plug and Play manager is attempting to redistribute the system's hardware resources.
. A user has indicated, typically by means of an application's user interface, that he or she wants to remove the device.
. The framework also calls the EvtCircuitPowerDown callback function after a device has been removed unexpectedly (surprise-removed).

For more information about when the framework calls this callback function, see PnP and Power Management Scenarios.

Unless the device has been surprise-removed, the ACX framework calls this callback function immediately after it disables the device's interrupts, but before the device's power is reduced from D0 and before WDF invokes the drivier's EvtDeviceD0Exit callback on the associated devices. The TargetState parameter identifies the device power state that the device is about to enter.

The EvtCircuitPowerDown callback function must perform any operations that are necessary before the ACXCIRCUT's hardware enters the specified low-power state, such as saving any information that the driver will need later to restore the ACXCIRCUIT's hardware to its D0 power state.

If TargetState is WdfPowerDeviceD3Final, you should assume that the system is being turned off, the associated device is about to be removed, or a resource rebalance is in progress. If your driver must save information, it should write it to disk or some other permanent storage medium.

For more information about drivers that provide this callback function, see Supporting PnP and Power Management in Function Drivers.

### Example

Example usage is shown below. This example shows stopping some timer instances in test code when the circuit powered down.


```cpp
EVT_ACX_CIRCUIT_POWER_DOWN          CodecR_EvtCircuitPowerDown;

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
CodecR_EvtCircuitPowerDown (
    _In_ WDFDEVICE  Device,
    _In_ ACXCIRCUIT Circuit,
    _In_ WDF_POWER_DEVICE_STATE TargetState
    )
{
    UNREFERENCED_PARAMETER(Device);
    UNREFERENCED_PARAMETER(TargetState);
    
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
    WdfTimerStop(muteCtx->Timer, TRUE);

    ASSERT(circuitCtx->VolumeElement);
    volumeCtx = GetCodecVolumeElementContext(circuitCtx->VolumeElement);
    ASSERT(volumeCtx);

    ASSERT(volumeCtx->Timer);
    WdfTimerStop(volumeCtx->Timer, TRUE);

    return STATUS_SUCCESS;
}
```

## -see-also

[acxcircuit.h header](index.md)

READY2GO