---
UID: NE:ntddndis._NDIS_IPV4_HEADER_FIELD
title: _NDIS_IPV4_HEADER_FIELD (ntddndis.h)
description: The NDIS_IPV4_HEADER_FIELD enumeration identifies the type of a field in an IP version 4 (IPv4) header to be filtered.
old-location: netvista\ndis_ipv4_header_field.htm
tech.root: netvista
ms.assetid: 5B7C4107-1724-473C-8F36-C345A056F3DC
ms.date: 05/02/2018
ms.keywords: "*PNDIS_IPV4_HEADER_FIELD, NDIS_IPV4_HEADER_FIELD, NDIS_IPV4_HEADER_FIELD enumeration [Network Drivers Starting with Windows Vista], NdisIPv4HeaderFieldMaximum, NdisIPv4HeaderFieldProtocol, NdisIPv4HeaderFieldUndefined, PNDIS_IPV4_HEADER_FIELD, PNDIS_IPV4_HEADER_FIELD enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_IPV4_HEADER_FIELD, netvista.ndis_ipv4_header_field, ntddndis/NDIS_IPV4_HEADER_FIELD, ntddndis/NdisIPv4HeaderFieldMaximum, ntddndis/NdisIPv4HeaderFieldProtocol, ntddndis/NdisIPv4HeaderFieldUndefined, ntddndis/PNDIS_IPV4_HEADER_FIELD"
ms.topic: enum
f1_keywords:
 - "ntddndis/NDIS_IPV4_HEADER_FIELD"
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
- NDIS_IPV4_HEADER_FIELD
product:
- Windows
targetos: Windows
req.typenames: NDIS_IPV4_HEADER_FIELD, *PNDIS_IPV4_HEADER_FIELD
---

# _NDIS_IPV4_HEADER_FIELD enumeration


## -description


The <b>NDIS_IPV4_HEADER_FIELD</b> enumeration identifies the type of a field in an IP version 4 (IPv4) header to be filtered.


## -enum-fields




### -field NdisIPv4HeaderFieldUndefined

An undefined IPV4 header field.


### -field NdisIPv4HeaderFieldProtocol

The IPv4 protocol field.


### -field NdisIPv4HeaderFieldMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks



The <b>NDIS_IPV4_HEADER_FIELD</b> enumeration is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_field_parameters">
    NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_field_parameters">
   NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a>
 

 

