---
UID: NS:hbapiwmi._MSFC_PortEvent
title: _MSFC_PortEvent
author: windows-driver-content
description: A WMI provider uses the MSFC_PortEvent structure to report port events for the indicated adapter.
old-location: storage\msfc_portevent.htm
old-project: storage
ms.assetid: bf9e2d58-9379-4b88-9043-580a97ec7cd9
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _MSFC_PortEvent, MSFC_PortEvent, *PMSFC_PortEvent
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
req.alt-api: MSFC_PortEvent
req.alt-loc: hbapiwmi.h
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
req.typenames: MSFC_PortEvent, *PMSFC_PortEvent
---

# _MSFC_PortEvent structure



## -description
A WMI provider uses the MSFC_PortEvent structure to report port events for the indicated adapter.



## -syntax

````
typedef struct _MSFC_PortEvent {
  ULONG EventType;
  ULONG FabricPortId;
  UCHAR PortWWN[8];
} MSFC_PortEvent, *PMSFC_PortEvent;
````


## -struct-fields

### -field EventType

Indicates the type of the event. The values that can be assigned to this member are defined by the <a href="https://msdn.microsoft.com/528e5eaa-aaeb-4e5b-a4b2-0f518fcd79ee">EVENT_TYPE_QUALIFIERS</a> WMI class qualifier.


### -field FabricPortId

Contains the fabric port ID. 


### -field PortWWN

Contains the worldwide name that indicates the port for which the event occurred. 


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/528e5eaa-aaeb-4e5b-a4b2-0f518fcd79ee">EVENT_TYPE_QUALIFIERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSFC_PortEvent structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

