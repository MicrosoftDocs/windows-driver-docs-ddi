---
UID: NC:acxelements.EVT_ACX_VOLUME_ASSIGN_LEVEL
tech.root: audio 
title: EVT_ACX_VOLUME_ASSIGN_LEVEL
ms.date: 04/29/2022
targetos: Windows
description: The EVT_ACX_VOLUME_ASSIGN_LEVEL callback function is implemented by the driver and is called when the volume level of a channel is set for a volume node. 
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
 - EVT_ACX_VOLUME_ASSIGN_LEVEL
f1_keywords:
 - EVT_ACX_VOLUME_ASSIGN_LEVEL
 - acxelements/EVT_ACX_VOLUME_ASSIGN_LEVEL
dev_langs:
 - c++
---

## -description

The **EVT_ACX_VOLUME_ASSIGN_LEVEL** callback function is implemented by the driver and is called when the volume level of a channel is set for a volume node. 

## -parameters

### -param Volume

An existing, initialized, ACXVOLUME object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). 

### -param Channel

A ULONG referring to a channel on the specified volume node. If this value is -1, then it refers to the master channel which represents the volume level for all channels on the volume node. 

### -param VolumeLevel

A LONG value that specifies the volume level of a channel in a volume node. If the channel value is -1 (referring to the master channel), then all channels on this volume node will be set to this volume level. Volume level values use the following scale:

-2147483648 is -infinity decibels (attenuation),

-2147483647 is -32767.99998474 decibels (attenuation), and

+2147483647 is +32767.99998474 decibels (gain).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
typedef struct _VOLUME_ELEMENT_CONTEXT {
    LONG            VolumeLevel[MAX_CHANNELS];
} VOLUME_ELEMENT_CONTEXT, *PVOLUME_ELEMENT_CONTEXT;

WDF_DECLARE_CONTEXT_TYPE_WITH_NAME(VOLUME_ELEMENT_CONTEXT, GetVolumeElementContext)

EVT_ACX_VOLUME_ASSIGN_LEVEL         CodecC_EvtVolumeAssignLevelCallback;

NTSTATUS
CodecC_EvtVolumeAssignLevelCallback(
    _In_    ACXVOLUME   Volume,
    _In_    ULONG       Channel,
    _In_    LONG        VolumeLevel
)
{
    PAGED_CODE();

    ASSERT(Volume);
    PVOLUME_ELEMENT_CONTEXT volumeCtx = GetVolumeElementContext(Volume);
    ASSERT(volumeCtx);

    if (Channel != ALL_CHANNELS_ID)
    {
        volumeCtx->VolumeLevel[Channel] = VolumeLevel;
    }
    else
    {
        for (ULONG i = 0; i < MAX_CHANNELS; ++i)
        {
            volumeCtx->VolumeLevel[i] = VolumeLevel;
        }
    }

    return STATUS_SUCCESS;
}
```

## -see-also

- [acxelements.h header](index.md)
