---
UID: NS:ndis._NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO
title: _NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO
author: windows-driver-content
description: The NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO structure specifies the security association (SA) offload handle to the tunnel portion of a send packet.
old-location: netvista\ndis_ipsec_offload_v2_tunnel_net_buffer_list_info.htm
old-project: netvista
ms.assetid: 3ca223a1-75d2-48b6-b4c2-f20e6fc57111
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/PNDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO, PNDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO, NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO structure [Network Drivers Starting with Windows Vista], ndis/NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO, netvista.ndis_ipsec_offload_v2_tunnel_net_buffer_list_info, PNDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO, *PNDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO, NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO, task_offload_IPsecv2_ref_1a564583-cac3-48d5-96f9-c6fecb5fadce.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: See Remarks section
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ndis.h
apiname: 
-	NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO
product: Windows
targetos: Windows
req.typenames: NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO, *PNDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO
---

# _NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO structure


## -description


<p class="CCE_Message">[The IPsec Task Offload feature is deprecated and should not be used.]

The NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO structure specifies the security association
  (SA) offload handle to the tunnel portion of a send packet.


## -syntax


````
typedef struct _NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO {
  struct {
    NDIS_HANDLE TunnelHandle;
  } Transmit;
} NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO, *PNDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO;
````


## -struct-fields




### -field Transmit

A structure that contains the following members:


### -field Transmit.TunnelHandle

The tunnel SA handle in transport over tunnel.


## -remarks


Before the TCP/IP transport passes a send packet that a NIC will perform Internet protocol security
    offload version 2 (IPsecOV2) tasks on to the miniport driver of the NIC, the transport updates the IPsec
    information in the 
    <mshelp:link keywords="netvista.ndis_ipsec_offload_v2_net_buffer_list_info" tabindex="0"><b>
    NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO</b></mshelp:link> structure that is associated with the 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.

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
    <mshelp:link keywords="netvista.oid_tcp_task_ipsec_offload_v2_add_sa" tabindex="0">
    OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</mshelp:link> request.

To set and get the IPsec tunnel information, use the 
    <b>IPsecOffloadV2TunnelNetBufferListInfo</b> index with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro.
    NET_BUFFER_LIST_INFO returns an NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO structure.



## -see-also

<mshelp:link keywords="netvista.ndis_ipsec_offload_v2_net_buffer_list_info" tabindex="0"><b>
   NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO</b></mshelp:link>

<mshelp:link keywords="netvista.oid_tcp_task_ipsec_offload_v2_add_sa" tabindex="0">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</mshelp:link>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<mshelp:link keywords="netvista.oid_tcp_task_ipsec_offload_v2_delete_sa" tabindex="0">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_DELETE_SA</mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

