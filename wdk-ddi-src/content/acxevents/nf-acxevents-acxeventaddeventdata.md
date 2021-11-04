---
UID: NF:acxevents.AcxEventAddEventData
tech.root: audio
title: AcxEventAddEventData
ms.date: 11/03/2021
targetos: Windows
description: TBD
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
 - AcxEventAddEventData
f1_keywords:
 - AcxEventAddEventData
 - acxevents/AcxEventAddEventData
dev_langs:
 - c++
---

## -description

The AcxEventAddEventData function adds event data to a and ACXEVENT object.

## -parameters

### -param Event

The ACXEVENT object (described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects)).

### -param EventData

The ACXEVENTDATA ACX object.

## -remarks

### Example

Example pending.

TBD - OK to use this test code?

```cpp
VOID
CodecR_EvtMuteElementChangeEventCallback(
    _In_        ACXOBJECT       Object,
    _In_        ACXEVENT        Event,
    _In_        ACX_EVENT_VERB  Verb,
    _In_opt_    ACXEVENTDATA    EventData,
    _In_opt_    WDFREQUEST      Request
    )
{
...
        AcxEventAddEventData(Event, EventData);
```

## -see-also

[acxcircuit.h header](index.md)



