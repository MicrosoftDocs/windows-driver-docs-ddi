---
UID: NC:acxelements.EVT_ACX_MUTE_RETRIEVE_STATE
tech.root: audio 
title: EVT_ACX_MUTE_RETRIEVE_STATE
ms.date: 09/16/2021
targetos: Windows
description: TBD - EVT_ACX_MUTE_RETRIEVE_STATE tells the driver that a request to retrieve the mute state has made???.
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

TBD - EVT_ACX_MUTE_RETRIEVE_STATE tells the driver that a request to retrieve the mute state has been made???.

## -parameters

### -param Mute

An existing, initialized, ACXMUTE object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). 

### -param Channel

TBD - A number that represents the channel that is active (present -TBD?)

### -param State

TBD - is this the desired or current mute state? 

TODO: This is a ulong, but wondering if it would better to reference a state enum such as ACX_STREAM_STATE?

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
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

[acxelements.h header](index.md)

