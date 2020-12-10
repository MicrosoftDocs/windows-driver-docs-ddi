---
UID: NF:portcls.IPortEvents.GenerateEventList
title: IPortEvents::GenerateEventList (portcls.h)
description: The GenerateEventList method notifies clients through the port driver's list of event entries that a particular event has occurred.
old-location: audio\iportevents_generateeventlist.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IPortEvents::GenerateEventList"]
ms.keywords: GenerateEventList, GenerateEventList method [Audio Devices], GenerateEventList method [Audio Devices],IPortEvents interface, IPortEvents interface [Audio Devices],GenerateEventList method, IPortEvents.GenerateEventList, IPortEvents::GenerateEventList, audio.iportevents_generateeventlist, audmp-routines_cc4243f5-90e9-471f-b8f0-aaf0945bddf5.xml, portcls/IPortEvents::GenerateEventList
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
req.irql: Any level. (See Remarks section.)
targetos: Windows
req.typenames: 
f1_keywords:
 - IPortEvents::GenerateEventList
 - portcls/IPortEvents::GenerateEventList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IPortEvents.GenerateEventList
---

# IPortEvents::GenerateEventList


## -description

The <code>GenerateEventList</code> method notifies clients through the port driver's list of event entries that a particular event has occurred.

## -parameters

### -param Set 

[in, optional]
Identifies the event set that the event belongs to. This parameter is a pointer to a GUID. <i>Set</i> is an optional parameter. A <i>Set</i> value of <b>NULL</b> is a wild card that matches all event-set GUIDs in the list. Otherwise, only event entries with matching event-set GUIDs are signaled.

### -param EventId 

[in]
Specifies an event ID. This parameter specifies the index of the event in the event set. If an event set contains <i>n</i> events, valid event IDs are in the range 0 to <i>n</i>-1. Only event entries with matching event IDs are signaled.

### -param PinEvent 

[in]
Specifies whether <i>PinId</i> should be used in qualifying which event entries to signal. If <i>PinEvent</i> is <b>FALSE</b>, <i>PinId</i> is treated as a wild card that matches all pin IDs in the list.

### -param PinId 

[in]
Specifies the pin ID of the event to be signaled. If <i>PinEvent</i> is <b>TRUE</b>, then only event entries with matching pin IDs are signaled.

### -param NodeEvent 

[in]
Indicates whether <i>NodeId</i> should be used in qualifying which event entries to signal. If <i>NodeEvent</i> is <b>FALSE</b>, <i>NodeId</i> is treated as a wild card that matches all node IDs in the list.

### -param NodeId 

[in]
Specifies the node ID of the event to be signaled. If <i>NodeEvent</i> is <b>TRUE</b>, then only event entries with matching node IDs are signaled.

## -remarks

This method is used by miniport drivers to signal event entries in the port driver's event list. In response to the miniport driver calling this method, the port driver walks its list of event entries and signals all registered event entries that meet the criteria expressed by the call parameters.

Although callers of <code>GenerateEventList</code> can be running at any IRQL, they are subject to some limitations when calling at IRQL > DISPATCH_LEVEL. Specifically, if the current implementation of <code>GenerateEventList</code> is called at IRQL > DISPATCH_LEVEL, the method queues a DPC to process the event list. That DPC contains the parameter context for a single call. As a result, signaling events might occasionally be missed if multiple calls are made at IRQL > DISPATCH_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nc-portcls-pcpfnevent_handler">EventHandler</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iportevents">IPortEvents</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iportevents-addeventtoeventlist">IPortEvents::AddEventToEventList</a>
