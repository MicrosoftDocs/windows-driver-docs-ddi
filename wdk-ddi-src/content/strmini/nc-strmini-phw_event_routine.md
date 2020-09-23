---
UID: NC:strmini.PHW_EVENT_ROUTINE
title: PHW_EVENT_ROUTINE (strmini.h)
description: The class driver calls the stream minidriver's StrMiniEvent routine to signal to a minidriver an event should be enabled or disabled.
old-location: stream\strminievent.htm
tech.root: stream
ms.assetid: 17f96498-3973-41f8-926d-85aa5f72de47
ms.date: 04/23/2018
keywords: ["PHW_EVENT_ROUTINE callback function"]
ms.keywords: PHW_EVENT_ROUTINE, StrMiniEvent, StrMiniEvent routine [Streaming Media Devices], stream.strminievent, strmini-routines_048c6591-7f69-44c2-8aa1-db42b5d718e0.xml, strmini/StrMiniEvent
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PHW_EVENT_ROUTINE
 - strmini/PHW_EVENT_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - strmini.h
api_name:
 - StrMiniEvent
---

# PHW_EVENT_ROUTINE callback function


## -description

The class driver calls the stream minidriver's <i>StrMiniEvent</i> routine to signal to a minidriver an event should be enabled or disabled.

## -parameters

### -param EventDescriptor 

[in]
Describes the event, and whether it should be enabled or disabled.

## -returns

For event enable events, <i>StrMiniEvent</i> returns STATUS_SUCCESS if the event is successfully enabled, or an error code on failure. The class driver ignores the return value on disable requests.

## -remarks

The class driver queues the <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry">KSEVENT_ENTRY</a> structure it passes in <i>EventDescriptor</i>-><b>EventEntry</b>. Every other member of <i>EventDescriptor</i> is deallocated once <i>StrMiniEvent</i> exits, so any event-specific data contained in the <b>EventData</b> member of <i>EventDescriptor</i> that the minidriver needs to keep should be stored by the minidriver.

For that purpose, the minidriver can allocate space directly after the KSEVENT_ENTRY structure by providing a nonzero value in the <b>ExtraEntryData</b> member of the <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksevent_item">KSEVENT_ITEM</a> structure it used to declare the event.