---
UID: NC:acxelements.EVT_ACX_VOLUME_RETRIEVE_LEVEL
tech.root: audio 
title: EVT_ACX_VOLUME_RETRIEVE_LEVEL
ms.date: 09/16/2021
targetos: Windows
description: TBD - EVT_ACX_VOLUME_RETRIEVE_LEVEL tells the driver that request to retrieve the volume level has made???.
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

TBD - EVT_ACX_VOLUME_RETRIEVE_LEVEL tells the driver that request to retrieve the volume level has made???.

## -parameters

### -param Volume

An existing, initialized, ACXVOLUME object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). 

### -param Channel

TBD - A number that represents the channel that is active (present -TBD?)

### -param VolumeLevel

TBD - assume fields matches KSAUDIOENGINE_VOLUMELEVEL structure???

Specifies the desired final volume level using the scale defined for the KSPROPERTY_AUDIOENGINE_VOLUMELEVEL property.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
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

[acxelements.h header](index.md)

