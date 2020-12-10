---
UID: NS:ndis._NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO
title: _NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO (ndis.h)
description: The NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO structure specifies information that is used in offloading Internet protocol security offload version 2 (IPsecOV2) tasks from the TCP/IP transport to a NIC.
old-location: netvista\ndis_ipsec_offload_v2_net_buffer_list_info.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO structure"]
ms.keywords: "*PNDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO, NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO, NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO, PNDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO, ndis/NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO, ndis/PNDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO, netvista.ndis_ipsec_offload_v2_net_buffer_list_info, task_offload_IPsecv2_ref_b675fa29-2688-43a5-8608-3fb750093a46.xml"
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
targetos: Windows
req.typenames: NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO, *PNDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO
f1_keywords:
 - _NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO
 - ndis/_NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO
 - PNDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO
 - ndis/PNDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO
 - NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO
 - ndis/NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO
---

# _NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO structure


## -description

<p class="CCE_Message">[The IPsec Task Offload feature is deprecated and should not be used.]

The <b>NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO</b> structure specifies information that is used in
  offloading Internet protocol security offload version 2 (IPsecOV2) tasks from the TCP/IP transport to a
  NIC.

## -struct-fields

### -field Transmit

A structure that contains the following members:

### -field Transmit.OffloadHandle

A handle to the outbound security association (SA) for a packet that has just one IPsec payload
       for a transport (end-to-end) connection.

### -field Receive

A structure that contains the following members:

### -field Receive.SaDeleteReq

A ULONG value that, when set, indicates that the TCP/IP transport should issue the 
       <a href="/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-delete-sa">
       OID_TCP_TASK_IPSEC_OFFLOAD_V2_DELETE_SA</a> OID once to delete the inbound SA that the packet was
       received over and once again to delete the outbound SA that corresponds to the deleted inbound SA. The
       network interface card (NIC) must not remove either of these SAs before it receives the corresponding
       OID_TCP_TASK_IPSEC_OFFLOAD_V2_DELETE_SA request.

### -field Receive.CryptoDone

A ULONG value that, when set, indicates that a NIC performed IPsec checking on at least one
       IPsec payload in the receive packet. When this value is cleared, it indicates that the NIC did not
       perform IPsec checking on the packet.

### -field Receive.NextCryptoDone

A ULONG value that, when set, indicates that a NIC performed IPsec checking on both the tunnel
       and transport portions of the receive packet. 
       <b>CryptoDone</b> must also be set in this case. 
       <b>NextCryptoDone</b> is set only if a packet has both tunnel and transport IPsec payloads; otherwise, 
       <b>NextCryptoDone</b> is set to zero.

### -field Receive.Reserved

Reserved for NDIS.

### -field Receive.CryptoStatus

The result of IPsec checking that a NIC performed on a receive packet. This result can be
       described as one of the following values:
       





##### CryptoStatus.CRYPTO_SUCCESS

The packet was successfully decrypted, if necessary, and the authentication header (AH)
         checksums, encapsulating security payload (ESP) checksums, or both checksums in the packet were
         validated.



##### CryptoStatus.CRYPTO_GENERIC_ERROR

The packet failed the IPsec check for an unspecified reason.



##### CryptoStatus.CRYPTO_TRANSPORT_AH_AUTH_FAILED

The AH checksum for the transport portion of the packet was invalid.



##### CryptoStatus.CRYPTO_TRANSPORT_ESP_AUTH_FAILED

The ESP checksum for the transport portion of the packet was invalid.



##### CryptoStatus.CRYPTO_TUNNEL_AH_AUTH_FAILED

The AH checksum for the tunnel portion of the packet was invalid.



##### CryptoStatus.CRYPTO_TUNNEL_ESP_AUTH_FAILED

The ESP checksum for the tunnel portion of the packet was invalid.



##### CryptoStatus.CRYPTO_INVALID_PACKET_SYNTAX

The receive packet's length is invalid. For example, the total length in the IP header is not
         sufficient to include all of the fields and headers for AH/ESP.



##### CryptoStatus.CRYPTO_INVALID_PROTOCOL

The IPsec protocols that were specified in the SA that the packet was received on do not match
         the IPsec protocols that were found in the packet. For example, this error occurs if the SA that the
         packet was received on specifies the AH protocol but the packet contained only an ESP header.

## -remarks

Before the TCP/IP transport passes an outbound packet to a NIC for offload processing, the transport
    specifies the IPsec information in the NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO structure that is
    associated with the 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure.

Specifically, the TCP/IP transport supplies a value for the 
    <b>OffloadHandle</b> member in the NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO structure. The 
    <b>OffloadHandle</b> value specifies the handle to the outbound SA for a packet that has just one IPsec
    payload, regardless of whether that payload is for a transport or a tunnel SA. The 
    <b>OffloadHandle</b> value that is supplied in the NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO structure
    has the same value as the 
    <b>OffloadHandle</b> value that was reported to the TCP/IP transport when the miniport driver successfully
    added a set of SAs to a NIC. All the SAs were added to the NIC when the miniport driver responded to an 
    <a href="/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-add-sa">
    OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</a> request.

Before a miniport driver indicates up a receive packet that has one or more IPsec payloads, the driver
    specifies IPsec information in the NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO structure that is
    associated with the 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure.

To set and get the IPsec information, use the 
    <b>IPsecOffloadV2NetBufferListInfo</b> index with the 
    <a href="/windows-hardware/drivers/network/net-buffer-list-info">NET_BUFFER_LIST_INFO</a> macro.
    NET_BUFFER_LIST_INFO returns the NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_ipsec_offload_v1_net_buffer_list_info">NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/network/net-buffer-list-info">NET_BUFFER_LIST_INFO</a>



<a href="/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-add-sa">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</a>



<a href="/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-delete-sa">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_DELETE_SA</a>
