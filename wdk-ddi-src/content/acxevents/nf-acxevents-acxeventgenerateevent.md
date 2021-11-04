---
UID: NF:acxevents.AcxEventGenerateEvent
tech.root: audio
title: AcxEventGenerateEvent
ms.date: 11/04/2021
targetos: Windows
description: The AcxEventGenerateEvent function generates an acx event.
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

The AcxEventGenerateEvent function generates an acx event.

## -parameters

### -param Event

The ACXEVENT object (described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects)).

## -remarks

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

[acxcircuit.h header](index.md)



