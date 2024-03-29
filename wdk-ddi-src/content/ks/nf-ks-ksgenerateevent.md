---
UID: NF:ks.KsGenerateEvent
title: KsGenerateEvent function (ks.h)
description: The KsGenerateEvent function generates a standard event notification given an event entry structure.
old-location: stream\ksgenerateevent.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsGenerateEvent function"]
ms.keywords: KsGenerateEvent, KsGenerateEvent function [Streaming Media Devices], ks/KsGenerateEvent, ksfunc_929fd3d4-2f02-4106-b8cd-25c3fb13ba05.xml, stream.ksgenerateevent
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: Any level (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - KsGenerateEvent
 - ks/KsGenerateEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsGenerateEvent
---

# KsGenerateEvent function


## -description

The <b>KsGenerateEvent</b> function generates a standard event notification given an event entry structure.

## -parameters

### -param EventEntry [in]


Specifies the event entry structure that references the event data. The information is used to determine what type of notification to perform. If the notification type is not one of the predefined standards, an error is returned. In the case of a single, nonrecurring event, this entry will be invalid on returning from the function. Therefore, any code that enumerates a list of events must preincrement to acquire the next event in the list before passing this event to the function.

## -returns

The <b>KsGenerateEvent</b> function returns STATUS_SUCCESS if successful, or if unsuccessful it returns an exception or memory error.

## -remarks

A device determines when event notifications are generated using the <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry">KSEVENT_ENTRY</a> structure, then uses this function to perform the actual notification. <b>KsGenerateEvent</b> can be called at any IRQL. If called above DISPATCH_LEVEL, signaling of the event will be performed asynchronously in a DPC.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfilteraddevent">KsFilterAddEvent</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergenerateevents">KsFilterGenerateEvents</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinaddevent">KsPinAddEvent</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspingenerateevents">KsPinGenerateEvents</a>
