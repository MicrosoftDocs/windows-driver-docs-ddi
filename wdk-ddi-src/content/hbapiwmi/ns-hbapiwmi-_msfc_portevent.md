---
UID: NS:hbapiwmi._MSFC_PortEvent
title: _MSFC_PortEvent (hbapiwmi.h)
description: A WMI provider uses the MSFC_PortEvent structure to report port events for the indicated adapter.
old-location: storage\msfc_portevent.htm
tech.root: storage
ms.assetid: bf9e2d58-9379-4b88-9043-580a97ec7cd9
ms.date: 03/29/2018
ms.keywords: "*PMSFC_PortEvent, MSFC_PortEvent, MSFC_PortEvent structure [Storage Devices], PMSFC_PortEvent, PMSFC_PortEvent structure pointer [Storage Devices], _MSFC_PortEvent, hbapiwmi/MSFC_PortEvent, hbapiwmi/PMSFC_PortEvent, storage.msfc_portevent, structs-Fibre_21739c44-07d2-412e-bc03-3cc25b14bb9d.xml"
ms.topic: struct
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hbapiwmi.h
api_name:
- MSFC_PortEvent
product:
- Windows
targetos: Windows
req.typenames: MSFC_PortEvent, *PMSFC_PortEvent
---

# _MSFC_PortEvent structure


## -description


A WMI provider uses the MSFC_PortEvent structure to report port events for the indicated adapter.


## -struct-fields




### -field EventType

Indicates the type of the event. The values that can be assigned to this member are defined by the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/event-types-qualifiers">EVENT_TYPE_QUALIFIERS</a> WMI class qualifier.


### -field FabricPortId

Contains the fabric port ID. 


### -field PortWWN

Contains the worldwide name that indicates the port for which the event occurred. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/event-types-qualifiers">EVENT_TYPE_QUALIFIERS</a>
 

 

