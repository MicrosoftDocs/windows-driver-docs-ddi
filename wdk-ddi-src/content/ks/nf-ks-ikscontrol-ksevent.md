---
UID: NF:ks.IKsControl.KsEvent
title: IKsControl::KsEvent (ks.h)
description: The IKsControl::KsEvent method enables or disables an event, together with any other defined support operations available on an event set.
old-location: stream\ikscontrol_ksevent2.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["IKsControl::KsEvent"]
ms.keywords: IKsControl interface [Streaming Media Devices],KsEvent method, IKsControl.KsEvent, IKsControl::KsEvent, KsEvent, KsEvent method [Streaming Media Devices], KsEvent method [Streaming Media Devices],IKsControl interface, avintfc_359de56d-5fcc-47ea-838c-cd110493856c.xml, ks/IKsControl::KsEvent, stream.ikscontrol_ksevent2
req.header: ks.h
req.include-header: Ks.h
req.target-type: DesktopMobile
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
 - IKsControl::KsEvent
 - ks/IKsControl::KsEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ks.h
api_name:
 - IKsControl.KsEvent
---

# IKsControl::KsEvent (ks.h)


## -description

The <b>IKsControl::KsEvent</b> method enables or disables an event, together with any other defined support operations available on an event set.

## -parameters

### -param Event

Pointer to a <a href="/previous-versions/ff561744(v=vs.85)">KSEVENT</a> structure that describes an event to enable the event and <b>NULL</b> to disable the event.

### -param EventLength

Specifies size, in bytes, of the buffer at <i>Event</i> when the event is enabled and zero when the event is disabled.

### -param EventData

Pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata">KSEVENTDATA</a> structure that contains data for the event and buffer space that receives data for the event.

### -param DataLength

Specifies size, in bytes, of the buffer at <i>EventData</i>.

### -param BytesReturned

Pointer to a variable that receives the size, in bytes, of the data that <b>KsEvent</b> stores in the buffer at <i>EventData</i>.

## -returns

The <b>IKsControl::KsEvent</b> method returns the same value that would be returned if the event had been sent by IOCTL.

## -remarks

To disable an event, set <i>Event</i> to <b>NULL</b>, <i>EventLength</i> to zero, and <i>EventData</i> to the pointer to the <a href="/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata">KSEVENTDATA</a> structure that was previously used to enable the event.

## -see-also

<a href="/previous-versions/ff561744(v=vs.85)">KSEVENT</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata">KSEVENTDATA</a>
