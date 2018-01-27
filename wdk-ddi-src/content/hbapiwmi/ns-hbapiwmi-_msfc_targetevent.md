---
UID: NS:hbapiwmi._MSFC_TargetEvent
title: _MSFC_TargetEvent
author: windows-driver-content
description: A WMI provider uses the MSFC_TargetEvent structure to report port events for the indicated adapter.
old-location: storage\msfc_targetevent.htm
old-project: storage
ms.assetid: e34e505c-74b1-45e4-9d9f-ba7cae111156
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _MSFC_TargetEvent, hbapiwmi/PMSFC_TargetEvent, MSFC_TargetEvent structure [Storage Devices], PMSFC_TargetEvent, PMSFC_TargetEvent structure pointer [Storage Devices], hbapiwmi/MSFC_TargetEvent, structs-Fibre_3f8b9bd0-29b2-43f3-85ae-47324d168956.xml, *PMSFC_TargetEvent, storage.msfc_targetevent, MSFC_TargetEvent
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	hbapiwmi.h
apiname: 
-	MSFC_TargetEvent
product: Windows
targetos: Windows
req.typenames: MSFC_TargetEvent, *PMSFC_TargetEvent
---

# _MSFC_TargetEvent structure


## -description


A WMI provider uses the MSFC_TargetEvent structure to report port events for the indicated adapter.


## -syntax


````
typedef struct _MSFC_TargetEvent {
  ULONG EventType;
  UCHAR PortWWN[8];
  UCHAR DiscoveredPortWWN[8];
} MSFC_TargetEvent, *PMSFC_TargetEvent;
````


## -struct-fields




### -field EventType

Indicates the type of the event. The values that can be assigned to this member are defined by the <a href="https://msdn.microsoft.com/528e5eaa-aaeb-4e5b-a4b2-0f518fcd79ee">EVENT_TYPE_QUALIFIERS</a> WMI class qualifier.


### -field PortWWN

Contains a worldwide name that indicates the local port for which the event occurred. 


### -field DiscoveredPortWWN

Contains a worldwide name that indicates the remote port for which the event occurred.


## -see-also

<a href="https://msdn.microsoft.com/528e5eaa-aaeb-4e5b-a4b2-0f518fcd79ee">EVENT_TYPE_QUALIFIERS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSFC_TargetEvent structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

