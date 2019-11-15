---
UID: NF:ks.KsPinGenerateEvents
title: KsPinGenerateEvents function (ks.h)
description: The KsPinGenerateEvents function generates events of an indicated type that are present in Pin's event list.
old-location: stream\kspingenerateevents.htm
tech.root: stream
ms.assetid: c2137849-aff0-4bf7-abab-b92e17aaef70
ms.date: 04/23/2018
ms.keywords: KsPinGenerateEvents, KsPinGenerateEvents function [Streaming Media Devices], avfunc_4bc7a2d8-139f-4f6e-b69c-46e05d8302e3.xml, ks/KsPinGenerateEvents, stream.kspingenerateevents
ms.topic: function
f1_keywords:
 - "ks/KsPinGenerateEvents"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
req.irql: <=DISPATCH_LEVEL (See Remarks)
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsPinGenerateEvents
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinGenerateEvents function

## -description

The **KsPinGenerateEvents** function generates events of an indicated type that are present in *Pin*'s event list.

## -parameters

### -param Pin [in]

A pointer to the [KSPIN](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin) structure on which to generate events.

### -param EventSet [in, optional]

A pointer to the event set GUID to match to determine which events to generate. If this parameter is **NULL**, set GUID is not taken into account for determining matching events.

### -param EventId [in]

The event ID to match to determine which events to generate.

### -param DataSize [in]

The size in bytes of the data with which to generate the data event.

### -param Data [in, optional]

A pointer to a data buffer. Specify if generating a data event.

### -param CallBack [in, optional]

A pointer to a caller-specified function that is called to determine whether a given event should be generated. If **NULL**, no callback verification is performed to determine whether an event should be generated (only *EventSet *and *EventId* are used). Prototype as follows:

```cpp
BOOLEAN CallBack
(IN PVOID Context,
    IN PKSEVENT_ENTRY EventEntry);
```

**KsPinGenerateEvents** passes the *CallBackContext* parameter unchanged as the *Context* parameter for the callback. The callback function returns **TRUE** if *EventEntry* should be generated. Otherwise, it returns **FALSE**.

### -param CallBackContext [in, optional]

A pointer to a caller-specified context that is passed to the callback function *CallBack*.

## -remarks

When calling this function, a minidriver must place *Data* and *CallBackContext* in a locked, nonpageable data segment. The *CallBack* is made at DISPATCH_LEVEL. The callback function must be in a locked segment and must be prepared to run at IRQL = DISPATCH_LEVEL. Note that there is an additional issue in DX8 *only*: *EventSet* must be in a locked data segment.

This is an inline function call to [KsGenerateEvents](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgenerateevents), which performs the necessary typecasting. Minidrivers should usually call this version instead of directly calling **KsGenerateEvents**.

An event is generated if the following three conditions hold:

* The event is present in *Pin's *event list and *EventId *matches the event's ID.

* *EventSet* either matches the event's set GUID or is **NULL**.

* *CallBack *is either **NULL** or authorizes the match.

For more information, see [Event Handling in AVStream](https://docs.microsoft.com/windows-hardware/drivers/stream/event-handling-in-avstream) and [KS Events](https://docs.microsoft.com/windows-hardware/drivers/stream/ks-events).

## -see-also

[KSEVENT_ENTRY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry)

[KsAddEvent](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksaddevent)

[KsFilterGenerateEvents](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergenerateevents)

[KsGenerateEvents](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgenerateevents)
