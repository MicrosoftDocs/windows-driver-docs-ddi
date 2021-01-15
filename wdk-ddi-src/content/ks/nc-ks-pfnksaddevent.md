---
UID: NC:ks.PFNKSADDEVENT
title: PFNKSADDEVENT (ks.h)
description: An AVStream minidriver's AVStrMiniAddEvent routine is called when a client registers to be notified of an event. This routine is optional.
old-location: stream\avstrminiaddevent.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["PFNKSADDEVENT callback function"]
ms.keywords: AVStrMiniAddEvent, AVStrMiniAddEvent routine [Streaming Media Devices], PFNKSADDEVENT, avstclbk_31147072-c3de-4b02-9fb1-b7f67765acc4.xml, ks/AVStrMiniAddEvent, stream.avstrminiaddevent
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PFNKSADDEVENT
 - ks/PFNKSADDEVENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ks.h
api_name:
 - PFNKSADDEVENT
---

# PFNKSADDEVENT callback function


## -description

An AVStream minidriver's <i>AVStrMiniAddEvent</i> routine is called when a client registers to be notified of an event. This routine is optional.

## -parameters

### -param Irp 

[in]
Specifies the IRP describing the event add request.

### -param EventData 

[in]
Pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata">KSEVENTDATA</a> structure describing the notification method for this event.

### -param EventEntry 

[in]
Pointer to an AVStream-generated <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry">KSEVENT_ENTRY</a> structure describing how the event is triggered.

## -returns

<i>AVStrMiniAddEvent</i> should return STATUS_SUCCESS or an error specific to the event being enabled.

## -remarks

If you do not provide an add event handler, AVStream adds the event to the object list. See <a href="/windows-hardware/drivers/stream/event-handling-in-avstream">Event Handling in AVStream</a>.

Frequently this callback implements vendor-specific behavior and then calls <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfilteraddevent">KsFilterAddEvent</a> or <a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinaddevent">KsPinAddEvent</a>. The minidriver passes the <i>EventEntry</i> pointer received here in calls to <i>KsFilterAddEvent</i> or <i>KsPinAddEvent</i>.

The minidriver specifies this routine's address in the <b>AddHandler</b> member of a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksevent_item">KSEVENT_ITEM</a> structure. <a href="/windows-hardware/drivers/stream/event-handling-in-avstream">Event Handling in AVStream</a> describes how the minidriver provides this structure to the class driver.

If an AVStream minidriver specifies <b>AddHandler</b> as non-NULL, AVStream does not add the item to the object's event list. If minidriver specifies an <b>AddHandler</b> and does not add the event to the object's event list through <b>KsDefaultAddEventHandler()</b> or a <b>Ks*AddEvent </b>call, the minidriver is responsible for cleaning up the event.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nc-ks-pfnksremoveevent">AVStrMiniRemoveEvent</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksautomation_table_">KSAUTOMATION_TABLE</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata">KSEVENTDATA</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry">KSEVENT_ENTRY</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksevent_item">KSEVENT_ITEM</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfilteraddevent">KsFilterAddEvent</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergenerateevents">KsFilterGenerateEvents</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinaddevent">KsPinAddEvent</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspingenerateevents">KsPinGenerateEvents</a>

