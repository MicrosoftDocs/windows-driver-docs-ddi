---
UID: NC:acxelements.EVT_ACX_RAMPED_VOLUME_ASSIGN_LEVEL
tech.root: audio 
title: EVT_ACX_RAMPED_VOLUME_ASSIGN_LEVEL
ms.date: 09/16/2021
targetos: Windows
description: TBD - EVT_ACX_RAMPED_VOLUME_ASSIGN_LEVEL tells the driver that a request to assign the ramped volume level has made???.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxelements.h
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
 - acxelements.h
api_name:
 - EVT_ACX_RAMPED_VOLUME_ASSIGN_LEVEL
f1_keywords:
 - EVT_ACX_RAMPED_VOLUME_ASSIGN_LEVEL
 - acxelements/EVT_ACX_RAMPED_VOLUME_ASSIGN_LEVEL
dev_langs:
 - c++
---

## -description

TBD - EVT_ACX_RAMPED_VOLUME_ASSIGN_LEVEL tells the driver that a request to assign the ramped volume level has been made???.

## -parameters

### -param Volume

An existing, initialized, ACXVOLUME object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). 

### -param Channel

TBD - A number that represents the channel that is active (present -TBD?)

### -param VolumeLevel

TBD - assume fields matches KSAUDIOENGINE_VOLUMELEVEL structure???

Specifies the desired final volume level using the scale defined for the KSPROPERTY_AUDIOENGINE_VOLUMELEVEL property.

### -param CurveType

Uses the AUDIO_CURVE_TYPE enumeration to specify the curve algorithm to apply over the duration specified, in order to reach the desired level. The curve begins at the current volume level and ends at the target volume level specified in the Volume parameter.

### -param CurveDuration

Specifies the duration, in hundreds of nanoseconds, over which the volume curve must take effect.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
EVT_ACX_RAMPED_VOLUME_ASSIGN_LEVEL              CodecR_EvtRampedVolumeAssignLevel;

NTSTATUS
NTAPI
CodecR_EvtRampedVolumeAssignLevel(
    _In_ ACXVOLUME              Volume,
    _In_ ULONG                  Channel,
    _In_ LONG                   VolumeLevel,
    _In_ ACX_VOLUME_CURVE_TYPE  CurveType,
    _In_ ULONGLONG              CurveDuration
    )
{
    PCODEC_VOLUME_ELEMENT_CONTEXT   volumeCtx;
    ULONG                           i;

    PAGED_CODE();

    UNREFERENCED_PARAMETER(CurveType);
    UNREFERENCED_PARAMETER(CurveDuration);

    volumeCtx = GetCodecVolumeElementContext(Volume);
    ASSERT(volumeCtx);

    if (Channel != ALL_CHANNELS_ID)
    {
        volumeCtx->VolumeLevel[Channel] = VolumeLevel;
    }
    else
    {
        for (i = 0; i < MAX_CHANNELS; ++i)
        {
            volumeCtx->VolumeLevel[i] = VolumeLevel;
        }
    }

    return STATUS_SUCCESS;
}
```

## -see-also

[acxelements.h header](index.md)

