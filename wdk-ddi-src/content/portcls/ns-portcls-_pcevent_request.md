---
UID: NS:portcls._PCEVENT_REQUEST
title: _PCEVENT_REQUEST (portcls.h)
description: The PCEVENT_REQUEST structure specifies an event request.
old-location: audio\pcevent_request.htm
tech.root: audio
ms.assetid: b28bd1c2-9fbe-4427-a4ba-5b79a338e913
ms.date: 05/08/2018
keywords: ["PCEVENT_REQUEST structure"]
ms.keywords: "*PPCEVENT_REQUEST, PCEVENT_REQUEST, PCEVENT_REQUEST structure [Audio Devices], PPCEVENT_REQUEST, PPCEVENT_REQUEST structure pointer [Audio Devices], _PCEVENT_REQUEST, audio.pcevent_request, audpc-struct_d60c4cf4-11e2-44b7-842a-65d965c8c422.xml, portcls/PCEVENT_REQUEST, portcls/PPCEVENT_REQUEST"
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
targetos: Windows
req.typenames: PCEVENT_REQUEST, *PPCEVENT_REQUEST
f1_keywords:
 - _PCEVENT_REQUEST
 - portcls/_PCEVENT_REQUEST
 - PPCEVENT_REQUEST
 - portcls/PPCEVENT_REQUEST
 - PCEVENT_REQUEST
 - portcls/PCEVENT_REQUEST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - portcls.h
api_name:
 - PCEVENT_REQUEST
---

# _PCEVENT_REQUEST structure


## -description

The <b>PCEVENT_REQUEST</b> structure specifies an event request.

## -struct-fields

### -field MajorTarget

<a href="https://docs.microsoft.com/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> pointer to the main miniport object. This member contains the <i>UnknownMiniport</i> pointer that the adapter driver previously passed to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iport-init">IPort::Init</a> method.

### -field MinorTarget

<a href="https://docs.microsoft.com/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> pointer to a stream object that is associated with the <i>MajorTarget</i> miniport object. This member contains the stream-object pointer that the port driver previously retrieved from the IMiniport<i>Xxx</i>::NewStream method (for example, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavecyclic-newstream">IMiniportWaveCyclic::NewStream</a> method's <i>Stream</i> parameter).

### -field Node

Specifies a node ID. This member identifies the target node for the request. If the target is not a node, this member is set to ULONG(-1).

### -field EventItem

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ns-portcls-pcevent_item">PCEVENT_ITEM</a> structure for this request

### -field EventEntry

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry">KSEVENT_ENTRY</a> structure for this request

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
Indicates that a client wants to enable the specified event. After validating the event and target information, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nc-portcls-pcpfnevent_handler">EventHandler</a> routine adds the event by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportevents-addeventtoeventlist">IPortEvents::AddEventToEventList</a> method.

</td>
</tr>
<tr>
<td>
PCEVENT_VERB_REMOVE

</td>
<td>
Notifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nc-portcls-pcpfnevent_handler">EventHandler</a> that an event is being disabled and removed from the list.

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

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> containing the event request

## -remarks

This is the structure that the port driver passes to the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nc-portcls-pcpfnevent_handler">EventHandler</a> routine. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ns-portcls-pcevent_item">PCEVENT_ITEM</a> structure contains a function pointer to an event handler that takes a <b>PCEVENT_REQUEST</b> pointer as its only call parameter. The port driver allocates a <b>PCEVENT_REQUEST</b> structure, extracts the relevant information from the original event request (which the <b>Irp</b> member points to), and loads the information into this structure before calling the handler.

In WDM audio, the target of an event request can be a pin instance but not a filter instance. The target can also include a node ID.

The <b>MajorTarget</b> and <b>MinorTarget</b> members are <a href="https://docs.microsoft.com/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> pointers to the main miniport object and an associated stream object, respectively. The event handler can query these objects for their miniport and stream interfaces.

For example, if the target for the event request is a pin instance on a WaveCyclic filter:

<ul>
<li>
The handler can call <a href="https://docs.microsoft.com/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)">QueryInterface</a> on the <b>MajorTarget</b> object's <a href="https://docs.microsoft.com/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface to obtain a reference to the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavecyclic">IMiniportWaveCyclic</a> interface.

</li>
<li>
The handler can call <a href="https://docs.microsoft.com/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)">QueryInterface</a> on the <b>MinorTarget</b> object's <a href="https://docs.microsoft.com/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface to obtain a reference to the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavecyclicstream">IMiniportWaveCyclicStream</a> interface.

</li>
</ul>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nc-portcls-pcpfnevent_handler">EventHandler</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportevents-addeventtoeventlist">IPortEvents::AddEventToEventList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry">KSEVENT_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ns-portcls-pcevent_item">PCEVENT_ITEM</a>



<a href="https://docs.microsoft.com/previous-versions/ff537695(v=vs.85)">PCFILTER_NODE</a>

