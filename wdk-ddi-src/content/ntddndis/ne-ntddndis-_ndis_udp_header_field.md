---
UID: NE:ntddndis._NDIS_UDP_HEADER_FIELD
title: _NDIS_UDP_HEADER_FIELD (ntddndis.h)
description: The NDIS_UDP_HEADER_FIELD enumeration identifies the type of a field in a User Datagram Protocol (UDP) header to be filtered.
old-location: netvista\ndis_udp_header_field.htm
tech.root: netvista
ms.assetid: 8AB1661D-A7DF-4178-8D1A-87A3AF9C4316
ms.date: 05/02/2018
ms.keywords: "*PNDIS_UDP_HEADER_FIELD, NDIS_UDP_HEADER_FIELD, NDIS_UDP_HEADER_FIELD enumeration [Network Drivers Starting with Windows Vista], NdisUdpHeaderFieldDestinationPort, NdisUdpHeaderFieldMaximum, NdisUdpHeaderFieldUndefined, PNDIS_UDP_HEADER_FIELD, PNDIS_UDP_HEADER_FIELD enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_UDP_HEADER_FIELD, netvista.ndis_udp_header_field, ntddndis/NDIS_UDP_HEADER_FIELD, ntddndis/NdisUdpHeaderFieldDestinationPort, ntddndis/NdisUdpHeaderFieldMaximum, ntddndis/NdisUdpHeaderFieldUndefined, ntddndis/PNDIS_UDP_HEADER_FIELD"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddndis.h
api_name:
- NDIS_UDP_HEADER_FIELD
product:
- Windows
targetos: Windows
req.typenames: NDIS_UDP_HEADER_FIELD, *PNDIS_UDP_HEADER_FIELD
---

# _NDIS_UDP_HEADER_FIELD enumeration


## -description


The <b>NDIS_UDP_HEADER_FIELD</b> enumeration identifies the type of a field in a User Datagram Protocol
(UDP) header to be filtered.


## -enum-fields




### -field NdisUdpHeaderFieldUndefined

An undefined UDP header field.


### -field NdisUdpHeaderFieldDestinationPort

The UDP destination port field.


### -field NdisUdpHeaderFieldMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks



The <b>NDIS_UDP_HEADER_FIELD</b> enumeration is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_receive_filter_field_parameters">
    NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_receive_filter_field_parameters">
   NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a>
 

 

