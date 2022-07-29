---
UID: NC:acxelements.EVT_ACX_VOLUME_RETRIEVE_LEVEL
tech.root: audio 
title: EVT_ACX_VOLUME_RETRIEVE_LEVEL
ms.date: 04/29/2022
targetos: Windows
description: The EVT_ACX_VOLUME_RETRIEVE_LEVEL callback function is implemented by the driver and is called when the volume level of a specified channel on a volume node is requested.
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
 - EVT_ACX_VOLUME_RETRIEVE_LEVEL
f1_keywords:
 - EVT_ACX_VOLUME_RETRIEVE_LEVEL
 - acxelements/EVT_ACX_VOLUME_RETRIEVE_LEVEL
dev_langs:
 - c++
---

## -description

The **EVT_ACX_VOLUME_RETRIEVE_LEVEL** callback function is implemented by the driver and is called when the volume level of a specified channel on a volume node is requested.

## -parameters

### -param Volume

An existing, initialized, ACXVOLUME object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). 

### -param Channel

A ULONG referring to a channel on the specified volume node. If this value is -1, then it refers to the master channel which sets the level for all channels on the volume node. 

### -param VolumeLevel

A LONG value that specifies the volume level of a channel in a given stream. Volumelevel values use the following scale:

-2147483648 is -infinity decibels (attenuation),

-2147483647 is -32767.99998474 decibels (attenuation), and

+2147483647 is +32767.99998474 decibels (gain).

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

EVT_ACX_VOLUME_RETRIEVE_LEVEL       CodecR_EvtVolumeRetrieveLevel;

NTSTATUS
NTAPI
CodecR_EvtVolumeRetrieveLevel(
    _In_  ACXVOLUME Volume,
    _In_  ULONG     Channel,
    _Out_ LONG *    VolumeLevel
)
{
    PCODEC_VOLUME_ELEMENT_CONTEXT   volumeCtx;

    PAGED_CODE();

    volumeCtx = GetCodecVolumeElementContext(Volume);
    ASSERT(volumeCtx);

    if (Channel != ALL_CHANNELS_ID)
    {
        *VolumeLevel = volumeCtx->VolumeLevel[Channel];
    }
    else
    {
        *VolumeLevel = volumeCtx->VolumeLevel[0];
    }

    return STATUS_SUCCESS;
}
```

## -see-also

- [acxelements.h header](index.md)

