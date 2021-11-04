---
UID: NC:acxevents.EVT_ACX_EVENT_DISABLE
tech.root: audio
title: EVT_ACX_EVENT_DISABLE
ms.date: 11/03/2021
targetos: Windows
description: TBD - The EVT_ACX_EVENT_DISABLE callback is used by the driver to add functionality when an ACX Event is being disabled TBD?
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxevents.h
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
 - acxevents.h
api_name:
 - EVT_ACX_EVENT_DISABLE
f1_keywords:
 - EVT_ACX_EVENT_DISABLE
 - acxevents/EVT_ACX_EVENT_DISABLE
dev_langs:
 - c++
---

## -description

TBD - The EVT_ACX_EVENT_DISABLE callback is used by the driver to add functionality when an ACX Event is being disabled TBD?

## -parameters

### -param Event

The ACXEVENT object (described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects)).

## -remarks

### Example

Example pending.

TBD - Is this code sample OK?

```cpp
EVT_ACX_EVENT_DISABLE               CodecR_EvtMuteElementDisableCallback;

VOID
CodecR_EvtMuteElementDisableCallback(
    _In_ ACXEVENT Event
    )
{
    CODEC_MUTE_EVENT_CONTEXT *  muteEventCtx;

    PAGED_CODE();
    
    // for testing. 
    muteEventCtx = GetCodecMuteEventContext(Event);
    ASSERT(muteEventCtx);
    
    ASSERT(muteEventCtx->Timer);
    WdfTimerStop(muteEventCtx->Timer, TRUE);
}
```


## -see-also

[acxcircuit.h header](index.md)



