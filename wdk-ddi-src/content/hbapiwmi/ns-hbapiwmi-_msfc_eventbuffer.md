---
UID: NS:hbapiwmi._MSFC_EventBuffer
title: _MSFC_EventBuffer (hbapiwmi.h)
description: The MSFC_EventBuffer structure is used in conjunction with the GetEventBuffer method to retrieve the next events in the HBA's event queue.
old-location: storage\msfc_eventbuffer.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["MSFC_EventBuffer structure"]
ms.keywords: "*PMSFC_EventBuffer, MSFC_EventBuffer, MSFC_EventBuffer structure [Storage Devices], PMSFC_EventBuffer, PMSFC_EventBuffer structure pointer [Storage Devices], _MSFC_EventBuffer, hbapiwmi/MSFC_EventBuffer, hbapiwmi/PMSFC_EventBuffer, storage.msfc_eventbuffer, structs-Fibre_d89430e7-c05b-4314-946e-fd8e70d938ac.xml"
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
req.typenames: MSFC_EventBuffer, *PMSFC_EventBuffer
f1_keywords:
 - _MSFC_EventBuffer
 - hbapiwmi/_MSFC_EventBuffer
 - PMSFC_EventBuffer
 - hbapiwmi/PMSFC_EventBuffer
 - MSFC_EventBuffer
 - hbapiwmi/MSFC_EventBuffer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - _MSFC_EventBuffer
 - PMSFC_EventBuffer
 - MSFC_EventBuffer
---

# _MSFC_EventBuffer structure


## -description

The MSFC_EventBuffer structure is used in conjunction with the <a href="/windows-hardware/drivers/storage/geteventbuffer">GetEventBuffer</a> method to retrieve the next events in the HBA's event queue.

## -struct-fields

### -field EventType

Indicates the type of the event. The values that can be assigned to this member are defined by the <a href="/windows-hardware/drivers/storage/event-types-qualifiers">EVENT_TYPE_QUALIFIERS</a> WMI class qualifier.

### -field EventInfo

Contains a structure of type <a href="/previous-versions/ff556048(v=vs.85)">HBA_EventInfo</a> that holds information about the events that were retrieved.

## -remarks

The WMI tool suite generates a declaration for this structure in <i>hbapiwm.h </i>after compiling the <a href="/windows-hardware/drivers/storage/msfc-eventbuffer-wmi-class">MSFC_EventBuffer WMI Class</a>. 

The <a href="/previous-versions/ff556048(v=vs.85)">HBA_EventInfo</a> structure is declared in <i>hbaapi.h</i>. You must include <i>hbaapi.h</i> to reference this structure.

## -see-also

<a href="/windows-hardware/drivers/storage/event-types-qualifiers">EVENT_TYPE_QUALIFIERS</a>



<a href="/windows-hardware/drivers/storage/geteventbuffer">GetEventBuffer</a>



<a href="/previous-versions/ff556048(v=vs.85)">HBA_EventInfo</a>

