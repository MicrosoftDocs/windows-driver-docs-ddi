---
UID: NS:hbapiwmi._MSFC_AdapterEvent
title: "_MSFC_AdapterEvent"
description: The MSFC_AdapterEvent structure is used by HBA miniport drivers that support the T11 committee's Fibre Channel HBA API specification to report adapter events to WMI clients that have registered to be notified of these events.
old-location: storage\msfc_adapterevent.htm
tech.root: storage
ms.assetid: 235300a1-3941-4f9c-8327-4ce174493f3e
ms.date: 03/29/2018
ms.keywords: "*PMSFC_AdapterEvent, MSFC_AdapterEvent, MSFC_AdapterEvent structure [Storage Devices], PMSFC_AdapterEvent, PMSFC_AdapterEvent structure pointer [Storage Devices], _MSFC_AdapterEvent, hbapiwmi/MSFC_AdapterEvent, hbapiwmi/PMSFC_AdapterEvent, storage.msfc_adapterevent, structs-Fibre_b76954f6-f00c-429d-8428-5cf1997cb40d.xml"
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
-	MSFC_AdapterEvent
product:
- Windows
targetos: Windows
req.typenames: MSFC_AdapterEvent, *PMSFC_AdapterEvent
---

# _MSFC_AdapterEvent structure


## -description


The MSFC_AdapterEvent structure is used by HBA miniport drivers that support the T11 committee's <i>Fibre Channel HBA API</i> specification to report adapter events to WMI clients that have registered to be notified of these events. 


## -struct-fields




### -field EventType

Indicates the type of the event. The values that can be assigned to this member are defined by the <a href="https://msdn.microsoft.com/528e5eaa-aaeb-4e5b-a4b2-0f518fcd79ee">EVENT_TYPE_QUALIFIERS</a> WMI class qualifier. 


### -field PortWWN

Contains the worldwide name of the port that generated the event. 


## -remarks



The WMI tool suite generates a declaration for this structure in <i>Hbapiwm.h </i>after compiling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562477">MSFC_AdapterEvent WMI Class</a>.

For more information about event types and worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.




## -see-also




<a href="https://msdn.microsoft.com/528e5eaa-aaeb-4e5b-a4b2-0f518fcd79ee">EVENT_TYPE_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562477">MSFC_AdapterEvent WMI Class</a>
 

 

