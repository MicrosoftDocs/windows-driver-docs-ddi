---
UID: NS:portcls._PCEVENT_REQUEST
title: "_PCEVENT_REQUEST"
author: windows-driver-content
description: The PCEVENT_REQUEST structure specifies an event request.
old-location: audio\pcevent_request.htm
old-project: audio
ms.assetid: b28bd1c2-9fbe-4427-a4ba-5b79a338e913
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PPCEVENT_REQUEST, PCEVENT_REQUEST, PCEVENT_REQUEST structure [Audio Devices], PPCEVENT_REQUEST, PPCEVENT_REQUEST structure pointer [Audio Devices], _PCEVENT_REQUEST, audio.pcevent_request, audpc-struct_d60c4cf4-11e2-44b7-842a-65d965c8c422.xml, portcls/PCEVENT_REQUEST, portcls/PPCEVENT_REQUEST"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: portcls.h
req.include-header: Portcls.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	portcls.h
api_name:
-	PCEVENT_REQUEST
product: Windows
targetos: Windows
req.typenames: PCEVENT_REQUEST, *PPCEVENT_REQUEST
---

# _PCEVENT_REQUEST structure


## -description


The <b>PCEVENT_REQUEST</b> structure specifies an event request.


## -struct-fields




### -field MajorTarget


<a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> pointer to the main miniport object. This member contains the <i>UnknownMiniport</i> pointer that the adapter driver previously passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a> method.


### -field MinorTarget


<a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> pointer to a stream object that is associated with the <i>MajorTarget</i> miniport object. This member contains the stream-object pointer that the port driver previously retrieved from the IMiniport<i>Xxx</i>::NewStream method (for example, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536723">IMiniportWaveCyclic::NewStream</a> method's <i>Stream</i> parameter).


### -field Node

Specifies a node ID. This member identifies the target node for the request. If the target is not a node, this member is set to ULONG(-1).


### -field EventItem

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537692">PCEVENT_ITEM</a> structure for this request


### -field EventEntry

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561853">KSEVENT_ENTRY</a> structure for this request


### -field Verb

Specifies the type of event request. This member should be set to one of the values in the following table.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
PCEVENT_VERB_ADD

</td>
<td>
Indicates that a client wants to enable the specified event. After validating the event and target information, the <a href="https://msdn.microsoft.com/06239870-8ed8-49c9-a9d4-fd3e28f3ab58">EventHandler</a> routine adds the event by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536886">IPortEvents::AddEventToEventList</a> method.

</td>
</tr>
<tr>
<td>
PCEVENT_VERB_REMOVE

</td>
<td>
Notifies the <a href="https://msdn.microsoft.com/06239870-8ed8-49c9-a9d4-fd3e28f3ab58">EventHandler</a> that an event is being disabled and removed from the list.

</td>
</tr>
<tr>
<td>
PCEVENT_VERB_SUPPORT

</td>
<td>
This request is a query for support. If the miniport driver supports the event for the target identified in the request, it should succeed this query. Otherwise, it should fail the query.

</td>
</tr>
<tr>
<td>
PCEVENT_VERB_NONE

</td>
<td>
No action is needed.

</td>
</tr>
</table>
 


### -field Irp

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> containing the event request


## -remarks



This is the structure that the port driver passes to the miniport driver's <a href="https://msdn.microsoft.com/06239870-8ed8-49c9-a9d4-fd3e28f3ab58">EventHandler</a> routine. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff537692">PCEVENT_ITEM</a> structure contains a function pointer to an event handler that takes a <b>PCEVENT_REQUEST</b> pointer as its only call parameter. The port driver allocates a <b>PCEVENT_REQUEST</b> structure, extracts the relevant information from the original event request (which the <b>Irp</b> member points to), and loads the information into this structure before calling the handler.

In WDM audio, the target of an event request can be a pin instance but not a filter instance. The target can also include a node ID.

The <b>MajorTarget</b> and <b>MinorTarget</b> members are <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> pointers to the main miniport object and an associated stream object, respectively. The event handler can query these objects for their miniport and stream interfaces.

For example, if the target for the event request is a pin instance on a WaveCyclic filter:

<ul>
<li>
The handler can call <a href="https://msdn.microsoft.com/54d5ff80-18db-43f2-b636-f93ac053146d">QueryInterface</a> on the <b>MajorTarget</b> object's <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface to obtain a reference to the object's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536714">IMiniportWaveCyclic</a> interface.

</li>
<li>
The handler can call <a href="https://msdn.microsoft.com/54d5ff80-18db-43f2-b636-f93ac053146d">QueryInterface</a> on the <b>MinorTarget</b> object's <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface to obtain a reference to the object's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536715">IMiniportWaveCyclicStream</a> interface.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/06239870-8ed8-49c9-a9d4-fd3e28f3ab58">EventHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536886">IPortEvents::AddEventToEventList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561853">KSEVENT_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537692">PCEVENT_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537695">PCFILTER_NODE</a>
 

 

