---
UID: NE:ntddndis._NDIS_MAC_PACKET_TYPE
title: "_NDIS_MAC_PACKET_TYPE"
author: windows-driver-content
description: The NDIS_MAC_PACKET_TYPE enumeration identifies the type of a destination address field in a media access control (MAC) header to be filtered.
old-location: netvista\ndis_mac_packet_type.htm
old-project: netvista
ms.assetid: 3cfa8fa4-fab0-4f94-abc1-5c7900af208b
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_MAC_PACKET_TYPE, NDIS_MAC_PACKET_TYPE, NDIS_MAC_PACKET_TYPE enumeration [Network Drivers Starting with Windows Vista], NdisMacPacketTypeBroadcast, NdisMacPacketTypeMaximum, NdisMacPacketTypeMulticast, NdisMacPacketTypeUndefined, NdisMacPacketTypeUnicast, PNDIS_MAC_PACKET_TYPE, PNDIS_MAC_PACKET_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_MAC_PACKET_TYPE, netvista.ndis_mac_packet_type, ntddndis/NDIS_MAC_PACKET_TYPE, ntddndis/NdisMacPacketTypeBroadcast, ntddndis/NdisMacPacketTypeMaximum, ntddndis/NdisMacPacketTypeMulticast, ntddndis/NdisMacPacketTypeUndefined, ntddndis/NdisMacPacketTypeUnicast, ntddndis/PNDIS_MAC_PACKET_TYPE"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_MAC_PACKET_TYPE
product: Windows
targetos: Windows
req.typenames: NDIS_MAC_PACKET_TYPE, *PNDIS_MAC_PACKET_TYPE
---

# _NDIS_MAC_PACKET_TYPE enumeration


## -description


The <b>NDIS_MAC_PACKET_TYPE</b> enumeration identifies the type of a destination address field in a media access control (MAC) header to be filtered.


## -enum-fields




### -field NdisMacPacketTypeUndefined

An undefined MAC packet type.


### -field NdisMacPacketTypeUnicast

A unicast MAC packet type.


### -field NdisMacPacketTypeMulticast

A multicast MAC packet type.


### -field NdisMacPacketTypeBroadcast

A broadcast MAC packet type.


### -field NdisMacPacketTypeMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks



The <b>NDIS_MAC_PACKET_TYPE</b> enumeration is used in the 
    <a href="https://msdn.microsoft.com/3d387fe9-a7cc-4034-b31e-ba1359db2ae1">
    NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/3d387fe9-a7cc-4034-b31e-ba1359db2ae1">
   NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MAC_PACKET_TYPE enumeration%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

