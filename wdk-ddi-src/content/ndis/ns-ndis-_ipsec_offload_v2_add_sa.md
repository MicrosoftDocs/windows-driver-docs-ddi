---
UID: NS:ndis._IPSEC_OFFLOAD_V2_ADD_SA
title: "_IPSEC_OFFLOAD_V2_ADD_SA"
author: windows-driver-content
description: The IPSEC_OFFLOAD_V2_ADD_SA structure defines information about a security association (SA) that a miniport driver should add to a NIC.
old-location: netvista\ipsec_offload_v2_add_sa.htm
tech.root: netvista
ms.assetid: 78c5e765-40e5-47f0-8460-a86124fb43d8
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: "*PIPSEC_OFFLOAD_V2_ADD_SA, IPSEC_OFFLOAD_V2_ADD_SA, IPSEC_OFFLOAD_V2_ADD_SA structure [Network Drivers Starting with Windows Vista], PIPSEC_OFFLOAD_V2_ADD_SA, PIPSEC_OFFLOAD_V2_ADD_SA structure pointer [Network Drivers Starting with Windows Vista], _IPSEC_OFFLOAD_V2_ADD_SA, ndis/IPSEC_OFFLOAD_V2_ADD_SA, ndis/PIPSEC_OFFLOAD_V2_ADD_SA, netvista.ipsec_offload_v2_add_sa, task_offload_IPsecv2_ref_0358b0f6-783e-4466-8615-12bd95ce4638.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and 6.20. For NDIS 6.30 and later, use IPSEC_OFFLOAD_V2_ADD_SA_EX.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	IPSEC_OFFLOAD_V2_ADD_SA
product:
- Windows
targetos: Windows
req.typenames: IPSEC_OFFLOAD_V2_ADD_SA, *PIPSEC_OFFLOAD_V2_ADD_SA
---

# _IPSEC_OFFLOAD_V2_ADD_SA structure


## -description


<p class="CCE_Message">[The IPsec Task Offload feature is deprecated and should not be used.]

The <b>IPSEC_OFFLOAD_V2_ADD_SA</b> structure defines information about a security association (SA) that a
  miniport driver should add to a NIC.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     IPSEC_OFFLOAD_V2_ADD_SA structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_IPSEC_OFFLOAD_V2_ADD_SA_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_IPSEC_OFFLOAD_V2_ADD_SA_REVISION_1.


### -field Next

A pointer to an IPSEC_OFFLOAD_V2_ADD_SA structure that is the next structure in a linked list. If
     the pointer is <b>NULL</b>, the current structure is the last structure in the list.


### -field NumExtHdrs

The number of IPsec extension headers. This member can be one of the following values.
     

<table>
<tr>
<th>Type of security</th>
<th>Extension headers</th>
</tr>
<tr>
<td>
AH authentication only

</td>
<td>
1

</td>
</tr>
<tr>
<td>
ESP authentication only

</td>
<td>
1

</td>
</tr>
<tr>
<td>
ESP encryption only

</td>
<td>
1

</td>
</tr>
<tr>
<td>
ESP authentication plus encryption

</td>
<td>
1

</td>
</tr>
<tr>
<td>
AH plus ESP authentication plus encryption

</td>
<td>
2

</td>
</tr>
<tr>
<td>
UDP ESP

</td>
<td>
1

</td>
</tr>
</table>
 


### -field Flags

A bitmask that indicates whether the SA that is being added is an inbound or outbound SA as
     follows:
     





#### IPSEC_OFFLOAD_V2_IPv6

If this flag is set, the addresses are IPv6. Otherwise, the addresses are IPv4





#### IPSEC_OFFLOAD_V2_INBOUND

If this flag is set, the SA is inbound. Otherwise, the SA is outbound.


### -field IPv4Endpoints

The IPv4 endpoint addresses. This structure contains the following members:


### -field IPv4Endpoints.SrcAddr

The IPv4 address of the source host (the host that is sending the packets).


### -field IPv4Endpoints.DestAddr

The IPv4 address of the destination host (the host that is receiving the packets).


### -field IPv6Endpoints

The IPv6 endpoint addresses. This structure contains the following members:


### -field IPv6Endpoints.SrcAddr

The IPv6 address of the source host (the host that is sending the packets).


### -field IPv6Endpoints.DestAddr

The IPv6 address of the destination host (the host that is receiving the packets).


### -field OffloadHandle

The handle to the newly created SA. The miniport driver supplies this handle before completing the     
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-add-sa">
     OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</a> request. The TCP/IP transport must specify this handle in the     
     <a href="https://msdn.microsoft.com/f528ae2f-54fc-4edc-99bf-b1958837584b">
     NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO</a> or 
     <a href="https://msdn.microsoft.com/3ca223a1-75d2-48b6-b4c2-f20e6fc57111">
     NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO</a> structure before passing a send packet to the
     miniport driver. The TCP/IP transport must also specify this handle when deleting the SA with an 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-delete-sa">
     OID_TCP_TASK_IPSEC_OFFLOAD_V2_DELETE_SA</a> request.


### -field UdpEspEncapsulation

The UDP ESP encapsulation type. This member can be one or more of the following flags:
     





#### IPSEC_OFFLOAD_V2_UDP_ESP_ENCAPSULATION_NONE

No UDP encapsulation is used.



#### IPSEC_OFFLOAD_V2_UDP_ESP_ENCAPSULATION_TRANSPORT

An ESP-encapsulated transport-mode packet is encapsulated by UDP.



#### IPSEC_OFFLOAD_V2_UDP_ESP_ENCAPSULATION_TUNNEL

The tunnel-mode portion of a packet is UDP-encapsulated. The transport-mode portion of the
       packet is not UDP-encapsulated and is not ESP-protected.



#### IPSEC_OFFLOAD_V2_TRANSPORT_OVER_UDP_ESP_ENCAPSULATION_TUNNEL

The tunnel-mode portion of a packet is UDP-encapsulated. The transport-mode portion of a packet
       is not UDP-encapsulated but is ESP-protected.



#### IPSEC_OFFLOAD_V2_UDP_ESP_ENCAPSULATION_TRANSPORT_OVER_TUNNEL

The tunnel-mode portion of a packet is not UDP-encapsulated. The transport-mode portion of a
       packet is UDP-encapsulated and ESP-protected.


### -field SecAssoc

An array with two elements that contain the information about the IPsec operations (AH, ESP, or
     both) for the SA. The number of provided elements is specified in the 
     <b>NumExtHdrs</b> member. The information for each IPsec operations is formatted as an 
     <a href="https://msdn.microsoft.com/b2c5611e-930d-41a5-a07e-7de8f8584283">
     IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION</a> structure, which is described below.
     

The TCP/IP transport specifies one or two IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION structures in the
     buffer at 
     <b>SecAssoc</b> . Each IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION structure indicates the type of
     operation--authentication or encryption/decryption--for which the SA specified in the structure is to be
     used. The order of the IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION structures in the array indicates the order
     in which the miniport driver should perform the operations for each SA. Only one combination of
     operations is supported: encryption/decryption (ESP) followed by authentication (AH).


### -field KeyLength

The length, in bytes, of the buffer at 
     <b>KeyData</b> .


### -field KeyData

A variable-length array that contains keys for the SAs that are specified at 
     <b>SecAssoc</b> . If both an encryption algorithm and an authentication algorithm are specified by the 
     <b>EncryptionAlgorithm</b> and 
     <b>AuthenticationAlgorithm</b> members of an 
     <a href="https://msdn.microsoft.com/b2c5611e-930d-41a5-a07e-7de8f8584283">
     IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION</a> structure, the buffer at 
     <b>KeyData</b> contains key information for one followed by the other. The beginning and the length of
     the key are specified by the 
     <b>KeyOffsetBytes</b> and 
     <b>KeyLength</b> members, respectively.


## -remarks



This structure is obsolete, use <a href="https://msdn.microsoft.com/library/windows/hardware/hh463943">IPSEC_OFFLOAD_V2_ADD_SA_EX</a> instead.

The IPSEC_OFFLOAD_V2_ADD_SA structure specifies a security SA that should be added and a pointer to
    the next IPSEC_OFFLOAD_V2_ADD_SA structure in a linked list. The IPSEC_OFFLOAD_V2_ADD_SA structure is
    used with the 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-add-sa">
    OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</a> OID.

The IPSEC_OFFLOAD_V2_ADD_SA structure specifies the source and destination, as well as the IP
    protocols, to which the SAs apply. This filter pertains to a transport-mode connection--that is, an
    end-to-end connection between two hosts. If the specified connection is made through a tunnel, the source
    and destination addresses of the tunnel are specified.

If a member is set to zero, that parameter is not used to filter packets for the specified SAs. For
    example, if 
    <b>SrcAddr</b> is set to zero, the specified SAs can apply to a packet that contains any source address.
    If all of the filter parameters are set to zero, the specified SAs apply to any source host that is
    sending any type of packet to any destination host.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh463943">IPSEC_OFFLOAD_V2_ADD_SA_EX</a>



<a href="https://msdn.microsoft.com/787e5a98-ba77-42d4-8624-abcc02fccf53">
   IPSEC_OFFLOAD_V2_ALGORITHM_INFO</a>



<a href="https://msdn.microsoft.com/b2c5611e-930d-41a5-a07e-7de8f8584283">
   IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION</a>



<a href="https://msdn.microsoft.com/f528ae2f-54fc-4edc-99bf-b1958837584b">
   NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO</a>



<a href="https://msdn.microsoft.com/3ca223a1-75d2-48b6-b4c2-f20e6fc57111">
   NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-add-sa">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-delete-sa">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_DELETE_SA</a>
 

 

