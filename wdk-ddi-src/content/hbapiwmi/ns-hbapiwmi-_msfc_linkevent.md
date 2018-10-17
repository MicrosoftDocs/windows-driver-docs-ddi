---
UID: NS:hbapiwmi._MSFC_LinkEvent
title: "_MSFC_LinkEvent"
author: windows-driver-content
description: A WMI provider uses the MSFC_LinkEvent structure to report link events for the indicated adapter.
old-location: storage\msfc_linkevent.htm
tech.root: storage
ms.assetid: 35fb3397-2e45-4d32-8cb1-1050199b2209
ms.date: 3/29/2018
ms.keywords: "*PMSFC_LinkEvent, MSFC_LinkEvent, MSFC_LinkEvent structure [Storage Devices], PMSFC_LinkEvent, PMSFC_LinkEvent structure pointer [Storage Devices], _MSFC_LinkEvent, hbapiwmi/MSFC_LinkEvent, hbapiwmi/PMSFC_LinkEvent, storage.msfc_linkevent, structs-Fibre_cbf79af7-ccf4-4996-b14d-bca141dece0e.xml"
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
-	MSFC_LinkEvent
product:
- Windows
targetos: Windows
req.typenames: MSFC_LinkEvent, *PMSFC_LinkEvent
---

# _MSFC_LinkEvent structure


## -description


A WMI provider uses the MSFC_LinkEvent structure to report link events for the indicated adapter.


## -struct-fields




### -field EventType

Indicates the type of the event. The values that can be assigned to this member are defined by the <a href="https://msdn.microsoft.com/528e5eaa-aaeb-4e5b-a4b2-0f518fcd79ee">EVENT_TYPE_QUALIFIERS</a> WMI class qualifier.


### -field AdapterWWN

Contains a worldwide name that indicates the adapter for which the event occurred. 


### -field RLIRBufferSize

Indicates the size of the buffer at <b>RLIRBuffer</b>. 


### -field RLIRBuffer

Contains the data associated with a register link incident request (RLIR).


## -see-also




<a href="https://msdn.microsoft.com/528e5eaa-aaeb-4e5b-a4b2-0f518fcd79ee">EVENT_TYPE_QUALIFIERS</a>
 

 

