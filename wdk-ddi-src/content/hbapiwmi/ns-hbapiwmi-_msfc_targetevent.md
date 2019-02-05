---
UID: NS:hbapiwmi._MSFC_TargetEvent
title: _MSFC_TargetEvent (hbapiwmi.h)
description: A WMI provider uses the MSFC_TargetEvent structure to report port events for the indicated adapter.
old-location: storage\msfc_targetevent.htm
tech.root: storage
ms.assetid: e34e505c-74b1-45e4-9d9f-ba7cae111156
ms.date: 03/29/2018
ms.keywords: "*PMSFC_TargetEvent, MSFC_TargetEvent, MSFC_TargetEvent structure [Storage Devices], PMSFC_TargetEvent, PMSFC_TargetEvent structure pointer [Storage Devices], _MSFC_TargetEvent, hbapiwmi/MSFC_TargetEvent, hbapiwmi/PMSFC_TargetEvent, storage.msfc_targetevent, structs-Fibre_3f8b9bd0-29b2-43f3-85ae-47324d168956.xml"
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hbapiwmi.h
api_name:
-	MSFC_TargetEvent
product:
- Windows
targetos: Windows
req.typenames: MSFC_TargetEvent, *PMSFC_TargetEvent
---

# _MSFC_TargetEvent structure


## -description


A WMI provider uses the MSFC_TargetEvent structure to report port events for the indicated adapter.


## -struct-fields




### -field EventType

Indicates the type of the event. The values that can be assigned to this member are defined by the <a href="https://msdn.microsoft.com/528e5eaa-aaeb-4e5b-a4b2-0f518fcd79ee">EVENT_TYPE_QUALIFIERS</a> WMI class qualifier.


### -field PortWWN

Contains a worldwide name that indicates the local port for which the event occurred. 


### -field DiscoveredPortWWN

Contains a worldwide name that indicates the remote port for which the event occurred.


## -see-also




<a href="https://msdn.microsoft.com/528e5eaa-aaeb-4e5b-a4b2-0f518fcd79ee">EVENT_TYPE_QUALIFIERS</a>
 

 

