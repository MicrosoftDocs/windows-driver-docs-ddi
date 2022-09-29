---
UID: NC:acxelements.EVT_ACX_MUTE_RETRIEVE_STATE
tech.root: audio 
title: EVT_ACX_MUTE_RETRIEVE_STATE
ms.date: 04/29/2022
targetos: Windows
description: The EVT_ACX_MUTE_RETRIEVE_STATE callback function is implemented by the driver and is called when the state of a specified channel on a mute node is requested. 
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
 - EVT_ACX_MUTE_RETRIEVE_STATE
f1_keywords:
 - EVT_ACX_MUTE_RETRIEVE_STATE
 - acxelements/EVT_ACX_MUTE_RETRIEVE_STATE
dev_langs:
 - c++
---

## -description

The **EVT_ACX_MUTE_RETRIEVE_STATE** callback function is implemented by the driver and is called when the state of a specified channel on a mute node is requested. 

## -parameters

### -param Mute

An existing, initialized, ACXMUTE object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). 

### -param Channel

A ULONG referring to a channel on the specified mute node. If this value is -1, then it refers to the master channel which represents the state of all channels on the mute node.

### -param State

A ULONG indicating the state of the specified channel on the mute node (i.e. whether or not the channel is muted). A value of 0 (FALSE) indicates the channel is not muted. A value of 1 (TRUE) indicates that the channel is muted. 

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

EVT_ACX_MUTE_RETRIEVE_STATE         CodecR_EvtMuteRetrieveState;

NTAPI
CodecR_EvtMuteRetrieveState(
    _In_  ACXMUTE   Mute,
    _In_  ULONG     Channel,
    _Out_ ULONG *   State
    )
{
    PCODEC_MUTE_ELEMENT_CONTEXT muteCtx;

    PAGED_CODE();

    muteCtx = GetCodecMuteElementContext(Mute);
    ASSERT(muteCtx);

    // use first channel for all channels setting.
    if (Channel != ALL_CHANNELS_ID)
    {
        *State = muteCtx->MuteState[Channel];
    }
    else
    {
        *State = muteCtx->MuteState[0];
    }

    return STATUS_SUCCESS;
}
```

## -see-also

- [acxelements.h header](index.md)
