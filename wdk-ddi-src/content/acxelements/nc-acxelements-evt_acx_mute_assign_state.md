---
UID: NC:acxelements.EVT_ACX_MUTE_ASSIGN_STATE
tech.root: audio 
title: EVT_ACX_MUTE_ASSIGN_STATE
ms.date: 04/29/2022
targetos: Windows
description: The EVT_ACX_MUTE_ASSIGN_STATE callback function is implemented by the driver and is called when the state of a specified channel on a mute node is set. 
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
 - EVT_ACX_MUTE_ASSIGN_STATE
f1_keywords:
 - EVT_ACX_MUTE_ASSIGN_STATE
 - acxelements/EVT_ACX_MUTE_ASSIGN_STATE
dev_langs:
 - c++
---

## -description

The **EVT_ACX_MUTE_ASSIGN_STATE** callback function is implemented by the driver and is called when the state of a specified channel on a mute node is set. The state of the channel can be set to 0 (FALSE) or 1 (TRUE), where 0 indicates the channel is not muted and 1 indicates the channel is muted.

## -parameters

### -param Mute

An existing, initialized, ACXMUTE object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). 

### -param Channel

A ULONG referring to a channel on the specified mute node. If this value is -1, then it refers to the master channel which represents the state for all channels on the mute node. 

### -param State

A ULONG indicating the state of the specified channel on the mute node (i.e. whether or not the channel is muted). A value of 0 (FALSE) indicates the channel is not muted. A value of 1 (TRUE) indicates that the channel is muted. If the channel value is -1 (referring to the master channel), then all channels on this mute node will be set to this state.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
typedef struct _CODEC_MUTE_ELEMENT_CONTEXT {
    BOOL            MuteState[MAX_CHANNELS]; 
} CODEC_MUTE_ELEMENT_CONTEXT, *PCODEC_MUTE_ELEMENT_CONTEXT;

WDF_DECLARE_CONTEXT_TYPE_WITH_NAME(CODEC_MUTE_ELEMENT_CONTEXT, GetCodecMuteElementContext)

EVT_ACX_MUTE_ASSIGN_STATE           CodecR_EvtMuteAssignState;

NTSTATUS
NTAPI
CodecR_EvtMuteAssignState(
    _In_ ACXMUTE    Mute,
    _In_ ULONG      Channel,
    _In_ ULONG      State
    )
{
    PCODEC_MUTE_ELEMENT_CONTEXT muteCtx;
    ULONG                       i;

    PAGED_CODE();

    muteCtx = GetCodecMuteElementContext(Mute);
    ASSERT(muteCtx);

    // use first channel for all channels setting.
    if (Channel != ALL_CHANNELS_ID)
    {
        muteCtx->MuteState[Channel] = State;
    }
    else
    {
        for (i = 0; i < MAX_CHANNELS; ++i)
        {
            muteCtx->MuteState[i] = State;
        }
    }

    return STATUS_SUCCESS;
}
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)
