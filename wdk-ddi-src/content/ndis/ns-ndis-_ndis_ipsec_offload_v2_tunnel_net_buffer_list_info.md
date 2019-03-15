---
UID: NS:ndis._NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO
title: _NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO (ndis.h)
description: The NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO structure specifies the security association (SA) offload handle to the tunnel portion of a send packet.
old-location: netvista\ndis_ipsec_offload_v2_tunnel_net_buffer_list_info.htm
tech.root: netvista
ms.assetid: 3ca223a1-75d2-48b6-b4c2-f20e6fc57111
ms.date: 05/02/2018
ms.keywords: "*PNDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO, NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO, NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO, PNDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO, ndis/NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO, ndis/PNDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO, netvista.ndis_ipsec_offload_v2_tunnel_net_buffer_list_info, task_offload_IPsecv2_ref_1a564583-cac3-48d5-96f9-c6fecb5fadce.xml"
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
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
- ndis.h
api_name:
- NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO
product:
- Windows
targetos: Windows
req.typenames: NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO, *PNDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO
---

# _NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO structure


## -description


<p class="CCE_Message">[The IPsec Task Offload feature is deprecated and should not be used.]

The NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO structure specifies the security association
  (SA) offload handle to the tunnel portion of a send packet.


## -struct-fields




### -field Transmit

A structure that contains the following members:


### -field Transmit.TunnelHandle

The tunnel SA handle in transport over tunnel.


## -remarks



Before the TCP/IP transport passes a send packet that a NIC will perform Internet protocol security
    offload version 2 (IPsecOV2) tasks on to the miniport driver of the NIC, the transport updates the IPsec
    information in the 
    <a href="https://msdn.microsoft.com/f528ae2f-54fc-4edc-99bf-b1958837584b">
    NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO</a> structure that is associated with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.

The TCP/IP transport supplies a handle in the 
    <b>OffloadHandle</b> member of NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO that specifies the handle to the
    outbound SA for the transport (end-to-end connection) portion of the send packet. If the send packet will
    be transmitted through a tunnel, the TCP/IP transport also supplies an
    NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO structure. This structure specifies the offload handle
    to the outbound SA for the tunnel portion of the send packet.

The 
    <b>TunnelHandle</b> value that is supplied in the NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO
    structure has the same value as the 
    <b>OffloadHandle</b> that was reported to the TCP/IP transport when the miniport driver successfully added
    a set of SAs to a NIC. All the SAs were added when the miniport driver responded to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-add-sa">
    OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</a> request.

To set and get the IPsec tunnel information, use the 
    <b>IPsecOffloadV2TunnelNetBufferListInfo</b> index with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro.
    NET_BUFFER_LIST_INFO returns an NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO structure.




## -see-also




<a href="https://msdn.microsoft.com/f528ae2f-54fc-4edc-99bf-b1958837584b">
   NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-add-sa">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-delete-sa">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_DELETE_SA</a>
 

 

