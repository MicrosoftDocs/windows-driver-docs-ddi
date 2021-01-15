---
UID: NE:ntddndis._NDIS_MAC_PACKET_TYPE
title: _NDIS_MAC_PACKET_TYPE (ntddndis.h)
description: The NDIS_MAC_PACKET_TYPE enumeration identifies the type of a destination address field in a media access control (MAC) header to be filtered.
old-location: netvista\ndis_mac_packet_type.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_MAC_PACKET_TYPE enumeration"]
ms.keywords: "*PNDIS_MAC_PACKET_TYPE, NDIS_MAC_PACKET_TYPE, NDIS_MAC_PACKET_TYPE enumeration [Network Drivers Starting with Windows Vista], NdisMacPacketTypeBroadcast, NdisMacPacketTypeMaximum, NdisMacPacketTypeMulticast, NdisMacPacketTypeUndefined, NdisMacPacketTypeUnicast, PNDIS_MAC_PACKET_TYPE, PNDIS_MAC_PACKET_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_MAC_PACKET_TYPE, netvista.ndis_mac_packet_type, ntddndis/NDIS_MAC_PACKET_TYPE, ntddndis/NdisMacPacketTypeBroadcast, ntddndis/NdisMacPacketTypeMaximum, ntddndis/NdisMacPacketTypeMulticast, ntddndis/NdisMacPacketTypeUndefined, ntddndis/NdisMacPacketTypeUnicast, ntddndis/PNDIS_MAC_PACKET_TYPE"
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
req.irql: 
targetos: Windows
req.typenames: NDIS_MAC_PACKET_TYPE, *PNDIS_MAC_PACKET_TYPE
f1_keywords:
 - _NDIS_MAC_PACKET_TYPE
 - ntddndis/_NDIS_MAC_PACKET_TYPE
 - PNDIS_MAC_PACKET_TYPE
 - ntddndis/PNDIS_MAC_PACKET_TYPE
 - NDIS_MAC_PACKET_TYPE
 - ntddndis/NDIS_MAC_PACKET_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - _NDIS_MAC_PACKET_TYPE
 - PNDIS_MAC_PACKET_TYPE
 - NDIS_MAC_PACKET_TYPE
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
    <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_field_parameters">
    NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_field_parameters">
   NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a>

