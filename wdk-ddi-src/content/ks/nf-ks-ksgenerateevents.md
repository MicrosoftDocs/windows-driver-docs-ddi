---
UID: NF:ks.KsGenerateEvents
title: KsGenerateEvents function (ks.h)
description: The KsGenerateEvents function generates events of an indicated type that are present in Object's event list.
old-location: stream\ksgenerateevents.htm
tech.root: stream
ms.assetid: 3c96012f-8307-417c-be8f-bb466c576669
ms.date: 04/23/2018
keywords: ["KsGenerateEvents function"]
ms.keywords: KsGenerateEvents, KsGenerateEvents function [Streaming Media Devices], avfunc_47306d1b-67f9-4ea6-81bb-3b76b848667a.xml, ks/KsGenerateEvents, stream.ksgenerateevents
f1_keywords:
 - "ks/KsGenerateEvents"
 - "KsGenerateEvents"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsGenerateEvents
targetos: Windows
req.typenames: 
---

# KsGenerateEvents function

## -description

The **KsGenerateEvents** function generates events of an indicated type that are present in *Object*'s event list.

## -parameters

### -param Object [in]

The object on which to generate events. This can be an AVStream filter or pin object.

### -param EventSet [in, optional]

The event set GUID to match to determine which events to generate. If this parameter is **NULL**, set GUID is not taken into account for determining matching events.

### -param EventId [in]

The event ID to match to determine which events to generate.

### -param DataSize [in]

The size in bytes of the data with which to generate the data event.

### -param Data [in, optional]

A pointer to a data buffer to include in the event notification. If the driver does not need to convey additional information via the notification, set this optional parameter to **NULL**.

### -param CallBack [in, optional]

A pointer to a caller-specified function that is called to determine whether a given event should be generated. If this is **NULL**, no callback verification is performed to determine whether an event should be generated (only *EventSet *and *EventId* are used).

### -param CallBackContext [in, optional]

A pointer to a caller-specified context that is passed to the callback function *CallBack*.

## -remarks

When calling this function, a minidriver must place *Data* and *CallBackContext* in a locked, nonpageable data segment. In addition, note that the *CallBack* is made at DISPATCH_LEVEL. The callback function must be in a locked segment and must be prepared to run at IRQL = DISPATCH_LEVEL. Note that there is an additional issue in DX8 *only*: *EventSet* must be in a locked data segment.

Minidrivers typically do not call this function directly and instead use one of the versions that performs appropriate casting: [KsFilterGenerateEvents](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergenerateevents) or [KsPinGenerateEvents](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingenerateevents).

An event is generated if it is present in *Object's *event list and *EventId *matches the event's ID, *EventSet* either matches the event's set GUID or is **NULL**, and *CallBack *is either **NULL** or authorizes the match.

*CallBack* is a caller-specified callback used for additional match determination. It is prototyped as follows:

```cpp
BOOLEAN CallBack (IN PVOID Context, IN PKSEVENT_ENTRY EventEntry);
```

AVStream passes the contents of the **KsGenerateEvents** routine's parameter *CallBackContext* in this callback's *Context* parameter. *EventEntry* is a pointer to a [KSEVENT_ENTRY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry) structure that specifies the event that would be generated. The callback function should return **TRUE** if this event should be generated.

For more information, see [Event Handling in AVStream](https://docs.microsoft.com/windows-hardware/drivers/stream/event-handling-in-avstream) and [KS Events](https://docs.microsoft.com/windows-hardware/drivers/stream/ks-events).

## -see-also

[KSEVENT_ENTRY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry)

[KsAddEvent](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksaddevent)

[KsFilterGenerateEvents](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergenerateevents)

[KsPinGenerateEvents](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingenerateevents)
