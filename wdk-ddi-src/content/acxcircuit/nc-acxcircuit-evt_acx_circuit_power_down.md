---
UID: NC:acxcircuit.EVT_ACX_CIRCUIT_POWER_DOWN
tech.root: audio
title: EVT_ACX_CIRCUIT_POWER_DOWN
ms.date: 08/23/2021
targetos: Windows
description: TBD - The EVT_ACX_CIRCUIT_POWER_DOWN callback is used by the driver to allow it to add additional functionality when a circuit is powered down using the TBD function is called,  TBD TBD. 
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

TBD - The EVT_ACX_CIRCUIT_POWER_DOWN callback is used by the driver to allow it to add additional functionality when a circuit is powered down using the TBD function is called,  TBD TBD. 

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that TBD has/is will be the parent under these conditions - TBD TBD 

### -param Circuit

TBD - An existing ACXCIRCUIT circuit object.  (DocsTeam - need link to ACX Object Summary topic).

### -param TargetState

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below. This example shows stopping some timer values for use in test code when the circuit powered up.


```cpp
EVT_ACX_CIRCUIT_POWER_DOWN          CodecR_EvtCircuitPowerDown;

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

