---
UID: NF:portcls.IPortEvents.AddEventToEventList
title: IPortEvents::AddEventToEventList (portcls.h)
description: The AddEventToEventList method adds an event to the port driver's event list.
old-location: audio\iportevents_addeventtoeventlist.htm
tech.root: audio
ms.assetid: 49b01942-3562-4fb2-907b-8863b2f09f8e
ms.date: 05/08/2018
keywords: ["IPortEvents::AddEventToEventList"]
ms.keywords: AddEventToEventList, AddEventToEventList method [Audio Devices], AddEventToEventList method [Audio Devices],IPortEvents interface, IPortEvents interface [Audio Devices],AddEventToEventList method, IPortEvents.AddEventToEventList, IPortEvents::AddEventToEventList, audio.iportevents_addeventtoeventlist, audmp-routines_13ea6aa7-0f65-43d4-b80c-4aa46102c43e.xml, portcls/IPortEvents::AddEventToEventList
req.header: portcls.h
req.include-header: Portcls.h
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IPortEvents::AddEventToEventList
 - portcls/IPortEvents::AddEventToEventList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IPortEvents.AddEventToEventList
---

# IPortEvents::AddEventToEventList


## -description

The <code>AddEventToEventList</code> method adds an event to the port driver's event list.

## -parameters

### -param EventEntry 

[in]
Pointer to the event entry that describes the event. This is an opaque system structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry">KSEVENT_ENTRY</a>.

## -remarks

This method is used by a miniport driver's to add events to the event list that is maintained by the associated port object. The miniport driver's event handler typically calls this method in response to a PCEVENT_VERB_ADD request after the handler has validated support for the event being requested.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nc-portcls-pcpfnevent_handler">EventHandler</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iportevents">IPortEvents</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportevents-generateeventlist">IPortEvents::GenerateEventList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry">KSEVENT_ENTRY</a>

