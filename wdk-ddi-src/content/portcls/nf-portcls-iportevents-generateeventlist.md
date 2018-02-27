---
UID: NF:portcls.IPortEvents.GenerateEventList
title: IPortEvents::GenerateEventList method
author: windows-driver-content
description: The GenerateEventList method notifies clients through the port driver's list of event entries that a particular event has occurred.
old-location: audio\iportevents_generateeventlist.htm
old-project: audio
ms.assetid: 99c9d60d-5f19-4b31-a8f3-aff69bc3a2a6
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: GenerateEventList method [Audio Devices], GenerateEventList method [Audio Devices], IPortEvents interface, GenerateEventList,IPortEvents.GenerateEventList, IPortEvents, IPortEvents interface [Audio Devices], GenerateEventList method, IPortEvents::GenerateEventList, audio.iportevents_generateeventlist, audmp-routines_cc4243f5-90e9-471f-b8f0-aaf0945bddf5.xml, portcls/IPortEvents::GenerateEventList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: portcls.h
req.dll: 
req.irql: Any level. (See Remarks section.)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPortEvents.GenerateEventList
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortEvents::GenerateEventList method


## -description


The <code>GenerateEventList</code> method notifies clients through the port driver's list of event entries that a particular event has occurred.


## -syntax


````
void GenerateEventList(
  [in, optional] GUID  *Set,
  [in]           ULONG EventId,
  [in]           BOOL  PinEvent,
  [in]           ULONG PinId,
  [in]           BOOL  NodeEvent,
  [in]           ULONG NodeId
);
````


## -parameters




### -param Set [in, optional]

Identifies the event set that the event belongs to. This parameter is a pointer to a GUID. <i>Set</i> is an optional parameter. A <i>Set</i> value of <b>NULL</b> is a wild card that matches all event-set GUIDs in the list. Otherwise, only event entries with matching event-set GUIDs are signaled.


### -param EventId [in]

Specifies an event ID. This parameter specifies the index of the event in the event set. If an event set contains <i>n</i> events, valid event IDs are in the range 0 to <i>n</i>-1. Only event entries with matching event IDs are signaled.


### -param PinEvent [in]

Specifies whether <i>PinId</i> should be used in qualifying which event entries to signal. If <i>PinEvent</i> is <b>FALSE</b>, <i>PinId</i> is treated as a wild card that matches all pin IDs in the list.


### -param PinId [in]

Specifies the pin ID of the event to be signaled. If <i>PinEvent</i> is <b>TRUE</b>, then only event entries with matching pin IDs are signaled.


### -param NodeEvent [in]

Indicates whether <i>NodeId</i> should be used in qualifying which event entries to signal. If <i>NodeEvent</i> is <b>FALSE</b>, <i>NodeId</i> is treated as a wild card that matches all node IDs in the list.


### -param NodeId [in]

Specifies the node ID of the event to be signaled. If <i>NodeEvent</i> is <b>TRUE</b>, then only event entries with matching node IDs are signaled.


## -returns



None




## -remarks



This method is used by miniport drivers to signal event entries in the port driver's event list. In response to the miniport driver calling this method, the port driver walks its list of event entries and signals all registered event entries that meet the criteria expressed by the call parameters.

Although callers of <code>GenerateEventList</code> can be running at any IRQL, they are subject to some limitations when calling at IRQL &gt; DISPATCH_LEVEL. Specifically, if the current implementation of <code>GenerateEventList</code> is called at IRQL &gt; DISPATCH_LEVEL, the method queues a DPC to process the event list. That DPC contains the parameter context for a single call. As a result, signaling events might occasionally be missed if multiple calls are made at IRQL &gt; DISPATCH_LEVEL.




## -see-also

<a href="..\portcls\nn-portcls-iportevents.md">IPortEvents</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536886">IPortEvents::AddEventToEventList</a>



<a href="..\portcls\nc-portcls-pcpfnevent_handler.md">EventHandler</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortEvents::GenerateEventList method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

