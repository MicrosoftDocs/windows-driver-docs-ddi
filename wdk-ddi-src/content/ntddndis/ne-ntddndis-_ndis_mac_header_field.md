---
UID: NE:ntddndis._NDIS_MAC_HEADER_FIELD
title: _NDIS_MAC_HEADER_FIELD (ntddndis.h)
description: The NDIS_MAC_HEADER_FIELD enumeration identifies the type of a field in a media access control (MAC) header to be filtered.
old-location: netvista\ndis_mac_header_field.htm
tech.root: netvista
ms.assetid: 31db285c-a7e7-4ba5-ba07-a60cfcfa9af9
ms.date: 05/02/2018
keywords: ["NDIS_MAC_HEADER_FIELD enumeration"]
ms.keywords: "*PNDIS_MAC_HEADER_FIELD, NDIS_MAC_HEADER_FIELD, NDIS_MAC_HEADER_FIELD enumeration [Network Drivers Starting with Windows Vista], NdisMacHeaderFieldDestinationAddress, NdisMacHeaderFieldMaximum, NdisMacHeaderFieldPacketType, NdisMacHeaderFieldPriority, NdisMacHeaderFieldProtocol, NdisMacHeaderFieldSourceAddress, NdisMacHeaderFieldUndefined, NdisMacHeaderFieldVlanId, PNDIS_MAC_HEADER_FIELD, PNDIS_MAC_HEADER_FIELD enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_MAC_HEADER_FIELD, netvista.ndis_mac_header_field, ntddndis/NDIS_MAC_HEADER_FIELD, ntddndis/NdisMacHeaderFieldDestinationAddress, ntddndis/NdisMacHeaderFieldMaximum, ntddndis/NdisMacHeaderFieldPacketType, ntddndis/NdisMacHeaderFieldPriority, ntddndis/NdisMacHeaderFieldProtocol, ntddndis/NdisMacHeaderFieldSourceAddress, ntddndis/NdisMacHeaderFieldUndefined, ntddndis/NdisMacHeaderFieldVlanId, ntddndis/PNDIS_MAC_HEADER_FIELD, virtual_machine_queue_ref_e521f802-ada1-444a-bf43-63405f40e45a.xml"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.typenames: NDIS_MAC_HEADER_FIELD, *PNDIS_MAC_HEADER_FIELD
f1_keywords:
 - _NDIS_MAC_HEADER_FIELD
 - ntddndis/_NDIS_MAC_HEADER_FIELD
 - PNDIS_MAC_HEADER_FIELD
 - ntddndis/PNDIS_MAC_HEADER_FIELD
 - NDIS_MAC_HEADER_FIELD
 - ntddndis/NDIS_MAC_HEADER_FIELD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_MAC_HEADER_FIELD
---

# _NDIS_MAC_HEADER_FIELD enumeration


## -description

The <b>NDIS_MAC_HEADER_FIELD</b> enumeration identifies the type of a field in a media access control (MAC) header to be filtered.

## -enum-fields

### -field NdisMacHeaderFieldUndefined

An undefined MAC header field.

### -field NdisMacHeaderFieldDestinationAddress

A destination address field.

### -field NdisMacHeaderFieldSourceAddress

A source address field.

### -field NdisMacHeaderFieldProtocol

A protocol field in the DEC/Intel/Xerox (DIX) Ethernet

MAC header.

### -field NdisMacHeaderFieldVlanId

A virtual local area network (VLAN) identifier field.

### -field NdisMacHeaderFieldPriority

A VLAN priority field.

### -field NdisMacHeaderFieldPacketType

A packet type field in the IEEE 802.2 subnetwork access protocol (SNAP) header of an 802.3

MAC header.

### -field NdisMacHeaderFieldMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.

## -remarks

The NDIS_MAC_HEADER_FIELD enumeration is used in the 
    <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_field_parameters">
    NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_field_parameters">
   NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a>