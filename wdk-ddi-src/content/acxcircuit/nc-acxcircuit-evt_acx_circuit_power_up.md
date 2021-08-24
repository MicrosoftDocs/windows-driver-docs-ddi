---
UID: NC:acxcircuit.EVT_ACX_CIRCUIT_POWER_UP
tech.root: audio
title: EVT_ACX_CIRCUIT_POWER_UP
ms.date: 08/20/2021
targetos: Windows
description: TBD - The EVT_ACX_CIRCUIT_POWER_UP callback is used by the driver to allow it to add additional functionality when a circuit is powered up using the TBD function is called,  TBD TBD. 
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
 - EVT_ACX_CIRCUIT_POWER_UP
f1_keywords:
 - EVT_ACX_CIRCUIT_POWER_UP
 - acxcircuit/EVT_ACX_CIRCUIT_POWER_UP
dev_langs:
 - c++
---

## -description

TBD - The EVT_ACX_CIRCUIT_POWER_UP callback is used by the driver to allow it to add additional functionality when a circuit is powered up using the TBD function is called,  TBD TBD. 

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that TBD has/is will be the parent under these conditions - TBD TBD 

### -param Circuit

TBD - An existing ACXCIRCUIT circuit object.  (DocsTeam - need link to ACX Object Summary topic).

### -param PreviousState

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below. This example shows starting some timer values for use in test code.

```cpp
EVT_ACX_CIRCUIT_POWER_UP            CodecR_EvtCircuitPowerUp;

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

## -see-also

[acxcircuit.h header](index.md)

