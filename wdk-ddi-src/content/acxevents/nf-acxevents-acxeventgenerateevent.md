---
UID: NF:acxevents.AcxEventGenerateEvent
tech.root: audio
title: AcxEventGenerateEvent
ms.date: 06/22/2022
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

An ACXEVENT represents an asynchronous notification available at the driver level. Events can be added to ACXCIRCUITs, ACXSTREAMs, ACXELEMENTs and ACXPINs. Internally they are exposed as KS events to upper layers. For more information about KS Events, see [KS Events](/windows-hardware/drivers/stream/ks-events).

### Example

This sample shows the use of AcxEventGenerateEvent.

```cpp
    PCODEC_MUTE_TIMER_CONTEXT timerCtx = GetCodecMuteTimerContext(Timer);
    PCODEC_MUTE_ELEMENT_CONTEXT muteCtx = GetCodecMuteElementContext(timerCtx->MuteElement);

    // Testing: update settings 0 <-> 1  
    muteCtx->MuteState[0] = !muteCtx->MuteState[0];
    muteCtx->MuteState[1] = !muteCtx->MuteState[1];
    
    AcxEventGenerateEvent(timerCtx->Event);
```

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxevents.h header](index.md)
