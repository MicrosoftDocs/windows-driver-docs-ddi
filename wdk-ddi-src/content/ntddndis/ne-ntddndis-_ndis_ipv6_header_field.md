---
UID: NE:ntddndis._NDIS_IPV6_HEADER_FIELD
title: _NDIS_IPV6_HEADER_FIELD (ntddndis.h)
description: The NDIS_IPV6_HEADER_FIELD enumeration identifies the type of a field in an IP version 6 (IPv6) header to be filtered.
old-location: netvista\ndis_ipv6_header_field.htm
tech.root: netvista
ms.assetid: 753BBA25-B0D5-4EBC-BA47-07ABEBCBA47D
ms.date: 05/02/2018
keywords: ["NDIS_IPV6_HEADER_FIELD enumeration"]
ms.keywords: "*PNDIS_IPV6_HEADER_FIELD, NDIS_IPV6_HEADER_FIELD, NDIS_IPV6_HEADER_FIELD enumeration [Network Drivers Starting with Windows Vista], NdisIPv6HeaderFieldMaximum, NdisIPv6HeaderFieldProtocol, NdisIPv6HeaderFieldUndefined, PNDIS_IPV6_HEADER_FIELD, PNDIS_IPV6_HEADER_FIELD enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_IPV6_HEADER_FIELD, netvista.ndis_ipv6_header_field, ntddndis/NDIS_IPV6_HEADER_FIELD, ntddndis/NdisIPv6HeaderFieldMaximum, ntddndis/NdisIPv6HeaderFieldProtocol, ntddndis/NdisIPv6HeaderFieldUndefined, ntddndis/PNDIS_IPV6_HEADER_FIELD"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later
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
req.typenames: NDIS_IPV6_HEADER_FIELD, *PNDIS_IPV6_HEADER_FIELD
f1_keywords:
 - _NDIS_IPV6_HEADER_FIELD
 - ntddndis/_NDIS_IPV6_HEADER_FIELD
 - PNDIS_IPV6_HEADER_FIELD
 - ntddndis/PNDIS_IPV6_HEADER_FIELD
 - NDIS_IPV6_HEADER_FIELD
 - ntddndis/NDIS_IPV6_HEADER_FIELD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_IPV6_HEADER_FIELD
---

# _NDIS_IPV6_HEADER_FIELD enumeration


## -description

The <b>NDIS_IPV6_HEADER_FIELD</b> enumeration identifies the type of a field in an IP version 6 (IPv6) header to be filtered.

## -enum-fields

### -field NdisIPv6HeaderFieldUndefined

An undefined IPv6 header field.

### -field NdisIPv6HeaderFieldProtocol

The IPv6 protocol field.

### -field NdisIPv6HeaderFieldMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.

## -remarks

The <b>NDIS_IPV6_HEADER_FIELD</b> enumeration is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_field_parameters">
    NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a> structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_field_parameters">
   NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a>

