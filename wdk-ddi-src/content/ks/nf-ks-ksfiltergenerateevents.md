---
UID: NF:ks.KsFilterGenerateEvents
title: KsFilterGenerateEvents function (ks.h)
description: The KsFilterGenerateEvents function generates events of an indicated type that are present in Filter's event list.
old-location: stream\ksfiltergenerateevents.htm
tech.root: stream
ms.assetid: 62340660-3419-4da6-8d58-c2f82b4231ba
ms.date: 04/23/2018
ms.keywords: KsFilterGenerateEvents, KsFilterGenerateEvents function [Streaming Media Devices], avfunc_bf12d7bb-6ebf-460b-a2c2-24632c89b083.xml, ks/KsFilterGenerateEvents, stream.ksfiltergenerateevents
ms.topic: function
f1_keywords:
 - "ks/KsFilterGenerateEvents"
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
req.irql: "<=DISPATCH_LEVEL (See Remarks section.)"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsFilterGenerateEvents
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsFilterGenerateEvents function

## -description

The **KsFilterGenerateEvents** function generates events of an indicated type that are present in *Filter*'s event list.

## -parameters

### -param Filter [in]

A pointer to a [KSFILTER](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksfilter) structure on which to generate events.

### -param EventSet [in, optional]

A pointer to the event set GUID to match for determination of which events to generate. If this parameter is **NULL**, the event set GUID is not taken into account for determining matching events.

### -param EventId [in]

The event ID to match for determining which events to generate.

### -param DataSize [in]

The size of *Data* in bytes.

### -param Data [in]

A pointer to a data buffer. Specify if generating a data event.

### -param CallBack [in, optional]

A pointer to a caller-specified function that is called to determine whether a given event should be generated. If this is **NULL**, no callback verification is performed to determine whether an event should be generated (only *EventSet *and *EventId* are used). For more information, see the Remarks section below.

### -param CallBackContext [in, optional]

An optional pointer to a caller-specified context that is passed to the callback function *CallBack*. For more information, see the Remarks section below.

## -returns

None

## -remarks

When calling this function, a minidriver must place *Data* and *CallBackContext* in a locked, nonpageable data segment. In addition, note that the *CallBack* is made at DISPATCH_LEVEL. The callback function must be in a locked segment and must be prepared to run at IRQL = DISPATCH_LEVEL. Note that there is an additional issue in DX8 *only*: *EventSet* must be in a locked data segment.

This is an inline function call to [KsGenerateEvents](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgenerateevents) that performs the necessary typecasting. Minidrivers should usually call this version instead of directly calling **KsGenerateEvents**.

An event is generated if the following conditions hold:

* The event is present in *Filter*'s event list and *EventId* matches the event's ID

* *EventSet* either matches the event's set GUID or is **NULL**

* *CallBack* is either **NULL** or authorizes the match

*CallBack* is a caller-specified callback used for additional match determination. It is prototyped as follows:

```cpp
BOOLEAN CallBack (IN PVOID Context, IN PKSEVENT_ENTRY EventEntry);
```

AVStream passes the contents of the **KsFilterGenerateEvents** routine's parameter *CallBackContext* in this callback's *Context* parameter. *EventEntry* is a pointer to a [KSEVENT_ENTRY](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksevent_entry) structure that specifies the event that would be generated. The callback function should return **TRUE** if this event should be generated.

For more information, see [Event Handling in AVStream](https://docs.microsoft.com/windows-hardware/drivers/stream/event-handling-in-avstream) and [KS Events](https://docs.microsoft.com/windows-hardware/drivers/stream/ks-events).

## -see-also

[KSEVENT_ENTRY](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksevent_entry)

[KsAddEvent](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksaddevent)

[KsGenerateEvents](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgenerateevents)

[KsPinGenerateEvents](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspingenerateevents)
