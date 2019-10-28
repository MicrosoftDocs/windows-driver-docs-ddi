---
UID: NC:portcls.PCPFNEVENT_HANDLER
title: PCPFNEVENT_HANDLER (portcls.h)
description: An EventHandler routine processes event requests.
old-location: audio\eventhandler.htm
tech.root: audio
ms.assetid: 06239870-8ed8-49c9-a9d4-fd3e28f3ab58
ms.date: 05/08/2018
ms.keywords: EventHandler, EventHandler callback function [Audio Devices], PCPFNEVENT_HANDLER, PCPFNEVENT_HANDLER callback, audio.eventhandler, audmp-routines_f75ad8d3-9abe-4f8a-97d4-605a18586ecb.xml, portcls/EventHandler
ms.topic: callback
f1_keywords:
 - "portcls/EventHandler"
req.header: portcls.h
req.include-header: Portcls.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- portcls.h
api_name:
- EventHandler
product:
- Windows
targetos: Windows
req.typenames: 
---

# PCPFNEVENT_HANDLER callback function


## -description


An <code>EventHandler</code> routine processes event requests.


## -parameters




### -param EventRequest [in]

Pointer to an initialized <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ns-portcls-_pcevent_request">PCEVENT_REQUEST</a> structure


## -returns



The event handler returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



Each event that a miniport driver exposes is associated with an event handler. The purpose of the event handler is to process event requests from the port driver and its clients. <i>EventRequest</i> is an input parameter to the handler that contains the following information about the event:

<ul>
<li>
The event set GUID and event ID.

</li>
<li>
How the event is to be triggered.

</li>
<li>
Pointers to the target miniport object and (for a pin) stream object.

</li>
</ul>
This is similar to the type of information that is provided with property requests.

The miniport driver exposes its event handlers through its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiport-getdescription">IMiniport::GetDescription</a> method. This method outputs a descriptor structure (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ns-portcls-pcfilter_descriptor">PCFILTER_DESCRIPTOR</a>) that defines the filter that the miniport driver and its associated port driver implement together. This structure contains a pointer to the miniport driver's automation table (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ns-portcls-pcautomation_table">PCAUTOMATION_TABLE</a>), which in turn contains a pointer to an array of the miniport driver's events. Each array element is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ns-portcls-pcevent_item">PCEVENT_ITEM</a> structure and contains a PCPFNEVENT_HANDLER function pointer to the handler for the event.

The <code>EventHandler</code> routine must reside in nonpaged memory.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiport-getdescription">IMiniport::GetDescription</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportevents-addeventtoeventlist">IPortEvents::AddEventToEventList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportevents-generateeventlist">IPortEvents::GenerateEventList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ns-portcls-pcautomation_table">PCAUTOMATION_TABLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ns-portcls-pcevent_item">PCEVENT_ITEM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ns-portcls-_pcevent_request">PCEVENT_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ns-portcls-pcfilter_descriptor">PCFILTER_DESCRIPTOR</a>
 

 

