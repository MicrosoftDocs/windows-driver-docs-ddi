---
UID: NE:ntddndis._NDIS_MAC_PACKET_TYPE
title: "_NDIS_MAC_PACKET_TYPE"
author: windows-driver-content
description: The NDIS_MAC_PACKET_TYPE enumeration identifies the type of a destination address field in a media access control (MAC) header to be filtered.
old-location: netvista\ndis_mac_packet_type.htm
old-project: netvista
ms.assetid: 3cfa8fa4-fab0-4f94-abc1-5c7900af208b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddndis/NdisMacPacketTypeUnicast, *PNDIS_MAC_PACKET_TYPE, ntddndis/NDIS_MAC_PACKET_TYPE, NdisMacPacketTypeBroadcast, ntddndis/NdisMacPacketTypeMaximum, NdisMacPacketTypeUnicast, PNDIS_MAC_PACKET_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], ntddndis/NdisMacPacketTypeMulticast, ntddndis/NdisMacPacketTypeBroadcast, NdisMacPacketTypeMaximum, PNDIS_MAC_PACKET_TYPE, NDIS_MAC_PACKET_TYPE, ntddndis/NdisMacPacketTypeUndefined, _NDIS_MAC_PACKET_TYPE, NdisMacPacketTypeUndefined, ntddndis/PNDIS_MAC_PACKET_TYPE, netvista.ndis_mac_packet_type, NDIS_MAC_PACKET_TYPE enumeration [Network Drivers Starting with Windows Vista], NdisMacPacketTypeMulticast
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
-	Ntddndis.h
apiname:
-	NDIS_MAC_PACKET_TYPE
product: Windows
targetos: Windows
req.typenames: NDIS_MAC_PACKET_TYPE, *PNDIS_MAC_PACKET_TYPE
---

# _NDIS_MAC_PACKET_TYPE enumeration


## -description


The <b>NDIS_MAC_PACKET_TYPE</b> enumeration identifies the type of a destination address field in a media access control (MAC) header to be filtered.


## -syntax


````
typedef enum _NDIS_MAC_PACKET_TYPE { 
  NdisMacPacketTypeUndefined  = 0,
  NdisMacPacketTypeUnicast    = 1,
  NdisMacPacketTypeMulticast  = 2,
  NdisMacPacketTypeBroadcast  = 3,
  NdisMacPacketTypeMaximum    = 4
} NDIS_MAC_PACKET_TYPE, *PNDIS_MAC_PACKET_TYPE;
````


## -enum-fields




#### - NdisMacPacketTypeUndefined

An undefined MAC packet type.


#### - NdisMacPacketTypeUnicast

A unicast MAC packet type.


#### - NdisMacPacketTypeMulticast

A multicast MAC packet type.


#### - NdisMacPacketTypeBroadcast

A broadcast MAC packet type.


#### - NdisMacPacketTypeMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks


The <b>NDIS_MAC_PACKET_TYPE</b> enumeration is used in the 
    <mshelp:link keywords="netvista.ndis_receive_filter_field_parameters" tabindex="0"><b>
    NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</b></mshelp:link> structure.



## -see-also

<mshelp:link keywords="netvista.ndis_receive_filter_field_parameters" tabindex="0"><b>
   NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MAC_PACKET_TYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

