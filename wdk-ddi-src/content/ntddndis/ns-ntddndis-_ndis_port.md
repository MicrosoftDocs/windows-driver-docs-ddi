---
UID: NS:ntddndis._NDIS_PORT
title: "_NDIS_PORT"
author: windows-driver-content
description: The NDIS_PORT structure specifies the characteristics of an NDIS port and a pointer to the next element in a linked list of ports.
old-location: netvista\ndis_port.htm
old-project: netvista
ms.assetid: aef1b7b2-73d3-49ad-a3f2-c06fa1f34839
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PNDIS_PORT structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PORT, NDIS_PORT, NDIS_PORT structure [Network Drivers Starting with Windows Vista], netvista.ndis_port, *PNDIS_PORT, PNDIS_PORT, ntddndis/PNDIS_PORT, ntddndis/NDIS_PORT, ndis_ports_ref_df9a02e1-4a6b-4901-8794-37a5e30ececb.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddndis.h
apiname:
-	NDIS_PORT
product: Windows
targetos: Windows
req.typenames: NDIS_PORT, *PNDIS_PORT
---

# _NDIS_PORT structure


## -description


The NDIS_PORT structure specifies the characteristics of an NDIS port and a pointer to the next
  element in a linked list of ports.


## -syntax


````
typedef struct _NDIS_PORT {
  PNDIS_PORT                Next;
  PVOID                     NdisReserved;
  PVOID                     MiniportReserved;
  PVOID                     ProtocolReserved;
  NDIS_PORT_CHARACTERISTICS PortCharacteristics;
} NDIS_PORT, *PNDIS_PORT;
````


## -struct-fields




### -field Next

A pointer to the next port in the linked list of ports.


### -field NdisReserved

Reserved for NDIS.


### -field MiniportReserved

Reserved for miniport drivers.


### -field ProtocolReserved

Reserved for protocol drivers.


### -field PortCharacteristics

An 
     <a href="..\ntddndis\ns-ntddndis-_ndis_port_characteristics.md">
     NDIS_PORT_CHARACTERISTICS</a> structure that specifies the characteristics of the port.


## -remarks



The NDIS_PORT structure is used to create a linked list of ports. Such a linked list is used in port
    activation (<b>NetEventPortActivation</b>) Plug and Play (PnP) events.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_port_characteristics.md">NDIS_PORT_CHARACTERISTICS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PORT structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

