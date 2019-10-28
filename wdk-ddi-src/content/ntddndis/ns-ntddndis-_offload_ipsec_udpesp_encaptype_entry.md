---
UID: NS:ntddndis._OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY
title: _OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY (ntddndis.h)
description: The OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY structure specifies the UDP-ESP encapsulation type and destination port of a parser entry.
old-location: netvista\offload_ipsec_udpesp_encaptype_entry.htm
tech.root: netvista
ms.assetid: a1e5ae2e-b183-4ccc-8413-1359c4e8a6bc
ms.date: 05/02/2018
ms.keywords: "*POFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY, 216offload_de874753-3127-47fb-8768-a5e2bd6eb96d.xml, OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY, OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY structure [Network Drivers Starting with Windows Vista], POFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY, POFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY structure pointer [Network Drivers Starting with Windows Vista], _OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY, netvista.offload_ipsec_udpesp_encaptype_entry, ntddndis/OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY, ntddndis/POFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY"
ms.topic: struct
f1_keywords:
 - "ntddndis/OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: 
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
- ntddndis.h
api_name:
- OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY
product:
- Windows
targetos: Windows
req.typenames: OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY, *POFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY
---

# _OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY structure


## -description


The OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY structure specifies the UDP-ESP encapsulation type and
  destination port of a parser entry.


## -struct-fields




### -field UdpEncapType

The UDP-ESP encapsulation type for packets protected by the security associations (SAs) that are
     being offloaded:
     





#### IPSEC_UDPESP_ENCAPTYPE_IKE

This value is reserved.



#### IPSEC_UDPESP_E\NCAPTYPE_OTHER

UDP encapsulation for packets on port 4500. For more information, see 
       <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff565707(v=vs.85)">UDP-ESP Encapsulation
       Types</a>.


### -field DstEncapPort

For an inbound SA (Flags = OFFLOAD_INBOUND_SA), specifies the destination port that the NIC should
     look for in the UDP header of inbound packets that it processes on the SAs being offloaded. The NIC
     should ignore this member for an outbound SA (
     <b>Flags</b> = 
     <b>OFFLOAD_OUTBOUND_SA</b>). 
     <b>DstEncapPort</b> should always specify port 4500.


## -remarks



The OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY structure is used with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_offload_ipsec_add_udpesp_sa">
    OFFLOAD_IPSEC_ADD_UDPESP_SA</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_offload_ipsec_add_udpesp_sa">OFFLOAD_IPSEC_ADD_UDPESP_SA</a>
 

 

