---
UID: NE:ntddndis._NDIS_FRAME_HEADER
title: _NDIS_FRAME_HEADER (ntddndis.h)
description: The NDIS_FRAME_HEADER enumeration identifies the type of header in a network data frame.
old-location: netvista\ndis_frame_header.htm
tech.root: netvista
ms.assetid: 8897ae0c-6068-4fea-8944-1340595dbff3
ms.date: 05/02/2018
ms.keywords: "*PNDIS_FRAME_HEADER, NDIS_FRAME_HEADER, NDIS_FRAME_HEADER enumeration [Network Drivers Starting with Windows Vista], NdisFrameHeaderArp, NdisFrameHeaderIPv4, NdisFrameHeaderIPv6, NdisFrameHeaderMac, NdisFrameHeaderMaximum, NdisFrameHeaderUdp, NdisFrameHeaderUndefined, PNDIS_FRAME_HEADER, PNDIS_FRAME_HEADER enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_FRAME_HEADER, netvista.ndis_frame_header, ntddndis/NDIS_FRAME_HEADER, ntddndis/NdisFrameHeaderArp, ntddndis/NdisFrameHeaderIPv4, ntddndis/NdisFrameHeaderIPv6, ntddndis/NdisFrameHeaderMac, ntddndis/NdisFrameHeaderMaximum, ntddndis/NdisFrameHeaderUdp, ntddndis/NdisFrameHeaderUndefined, ntddndis/PNDIS_FRAME_HEADER, virtual_machine_queue_ref_0ee94de6-7791-4a6e-b3da-2c8639843130.xml"
ms.topic: enum
f1_keywords:
 - "ntddndis/NDIS_FRAME_HEADER"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddndis.h
api_name:
- NDIS_FRAME_HEADER
product:
- Windows
targetos: Windows
req.typenames: NDIS_FRAME_HEADER, *PNDIS_FRAME_HEADER
---

# _NDIS_FRAME_HEADER enumeration


## -description


The <b>NDIS_FRAME_HEADER</b> enumeration identifies the type of header in a network data frame.


## -enum-fields




### -field NdisFrameHeaderUndefined

An undefined frame header type.


### -field NdisFrameHeaderMac

A media access control (MAC) header.


### -field NdisFrameHeaderArp

An Address Resolution Protocol (ARP) header.


### -field NdisFrameHeaderIPv4

An IP version 4 (IPv4) header.


### -field NdisFrameHeaderIPv6

An IP version 6 (IPv6) header.


### -field NdisFrameHeaderUdp

A User Datagram Protocol
(UDP) header.


### -field NdisFrameHeaderMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks



The NDIS_FRAME_HEADER enumeration is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_field_parameters">
    NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_field_parameters">
   NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a>
 

 

