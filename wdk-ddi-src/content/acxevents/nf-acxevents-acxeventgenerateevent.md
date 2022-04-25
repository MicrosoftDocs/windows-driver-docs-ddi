---
UID: NF:acxevents.AcxEventGenerateEvent
tech.root: audio
title: AcxEventGenerateEvent
ms.date: 12/09/2021
targetos: Windows
description: The AcxEventGenerateEvent function generates an event.
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
 - AcxEventGenerateEvent
f1_keywords:
 - AcxEventGenerateEvent
 - acxevents/AcxEventGenerateEvent
dev_langs:
 - c++
---

## -description

The **AcxEventGenerateEvent** function generates an ACX event.

## -parameters

### -param Event

The ACXEVENT object (described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects)).

## -remarks

An AcxEvent represents an asynchronous notification available at the driver level. Events can be added to AcxCircuits, AcxStreams, AcxElements and AcxPins. Internally they are exposed as KS events to upper layers. 

### Example

TBD - Is there anything we should add to this sample code from the test driver?

This sample shows the use of AcxEventGenerateEvent.

```cpp
    PCODEC_MUTE_TIMER_CONTEXT timerCtx = GetCodecMuteTimerContext(Timer);
    PCODEC_MUTE_ELEMENT_CONTEXT muteCtx = GetCodecMuteElementContext(timerCtx->MuteElement);

    // update settings 0 <-> 1  
    muteCtx->MuteState[0] = !muteCtx->MuteState[0];
    muteCtx->MuteState[1] = !muteCtx->MuteState[1];
    
    AcxEventGenerateEvent(timerCtx->Event);
```

## -see-also

- [acxevents.h header](index.md)

TBD - Please review this topic

