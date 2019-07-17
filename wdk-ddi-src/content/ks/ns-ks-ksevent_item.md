---
UID: NS:ks.__unnamed_struct_72
title: KSEVENT_ITEM (ks.h)
description: The KSEVENT_ITEM structure describe a minidriver's support for a specific event within an event set.
old-location: stream\ksevent_item.htm
tech.root: stream
ms.assetid: a501a693-bea1-43eb-af8c-5512c8ee9d50
ms.date: 04/23/2018
ms.keywords: "*PKSEVENT_ITEM, KSEVENT_ITEM, KSEVENT_ITEM structure [Streaming Media Devices], PKSEVENT_ITEM, PKSEVENT_ITEM structure pointer [Streaming Media Devices], ks-struct_1e126443-3eef-4e67-9969-69c3a4aaa17c.xml, ks/KSEVENT_ITEM, ks/PKSEVENT_ITEM, stream.ksevent_item"
ms.topic: struct
f1_keywords:
 - "ks/KSEVENT_ITEM"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KSEVENT_ITEM
product:
- Windows
targetos: Windows
req.typenames: KSEVENT_ITEM, *PKSEVENT_ITEM
---

# KSEVENT_ITEM structure


## -description


The KSEVENT_ITEM structure describe a minidriver's support for a specific event within an event set.


## -struct-fields




### -field EventId

Specifies the unique ID of the event within the event set.


### -field DataInput

Specifies the size in bytes of event data. The event data begins with a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-kseventdata">KSEVENTDATA</a> structure that describes how the client should be notified when the event occurs, optionally followed by any additional parameters that specify when the event occurs. Must be at least <b>sizeof</b>(KSEVENTDATA).


### -field ExtraEntryData

Specifies the size in bytes of any additional memory that the system should allocate for each enable request for this event. The driver uses this memory to store any data it needs to keep track of the event request. The memory is allocated directly after the event enable request's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksevent_entry">KSEVENT_ENTRY</a> structure.


### -field AddHandler

Pointer to a minidriver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnksaddevent">AVStrMiniAddEvent</a> callback routine. Not used by the stream class driver. For AVStream minidrivers only.


### -field RemoveHandler

Pointer to a minidriver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnksremoveevent">AVStrMiniRemoveEvent</a> callback routine. Not used by the stream class driver. For AVStream minidrivers only.


### -field SupportHandler

Not used by the stream class driver.


## -remarks



<i>A minidriver that specifies the </i><b>AddHandler</b><i> and </i><b>RemoveHandler</b><i> members and does not properly clean the events up can cause a resource (memory/handle) leak.</i>




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ni-ks-ioctl_ks_disable_event">IOCTL_KS_DISABLE_EVENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-kseventdata">KSEVENTDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksevent_entry">KSEVENT_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksdefaultaddeventhandler">KsDefaultAddEventHandler</a>
 

 

