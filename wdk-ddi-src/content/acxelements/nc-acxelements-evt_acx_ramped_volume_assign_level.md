---
UID: NC:acxelements.EVT_ACX_RAMPED_VOLUME_ASSIGN_LEVEL
tech.root: audio 
title: EVT_ACX_RAMPED_VOLUME_ASSIGN_LEVEL
ms.date: 04/29/2022
targetos: Windows
description: EVT_ACX_RAMPED_VOLUME_ASSIGN_LEVEL is implemented by the driver and is called when the volume level of a channel is set for a volume node.
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

The **EVT_ACX_RAMPED_VOLUME_ASSIGN_LEVEL** callback is implemented by the driver and is called when the volume level of a channel is set for a volume node.

## -parameters

### -param Volume

An existing, initialized, ACXVOLUME object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). 

### -param Channel

A ULONG referring to a channel on the specified volume node. If this value is -1, then it refers to the master channel which represents the volume level for all channels on the volume node.

### -param VolumeLevel

A LONG value that specifies the desired final volume level for the given channel. If the channel value is -1 (referring to the master channel), then all channels on this volume node will be set to this volume level. Volume level values use the following scale:

-2147483648 is -infinity decibels (attenuation),

-2147483647 is -32767.99998474 decibels (attenuation), and

+2147483647 is +32767.99998474 decibels (gain).

### -param CurveType

Uses the [AUDIO_CURVE_TYPE enumeration](/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-audio_curve_type) to specify the curve algorithm to apply over the duration specified, in order to reach the desired level. The curve begins at the current volume level and ends at the target volume level specified in the Volume parameter.

### -param CurveDuration

Specifies the duration, in hundreds of nanoseconds, over which the volume curve must take effect.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
typedef struct _CODEC_VOLUME_ELEMENT_CONTEXT {
    LONG            VolumeLevel[MAX_CHANNELS];
} CODEC_VOLUME_ELEMENT_CONTEXT, *PCODEC_VOLUME_ELEMENT_CONTEXT;

WDF_DECLARE_CONTEXT_TYPE_WITH_NAME(CODEC_VOLUME_ELEMENT_CONTEXT, GetCodecVolumeElementContext)

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

- [acxelements.h header](index.md)
