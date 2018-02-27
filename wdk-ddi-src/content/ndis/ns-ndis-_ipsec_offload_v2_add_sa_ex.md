---
UID: NS:ndis._IPSEC_OFFLOAD_V2_ADD_SA_EX
title: "_IPSEC_OFFLOAD_V2_ADD_SA_EX"
author: windows-driver-content
description: The IPSEC_OFFLOAD_V2_ADD_SA_EX structure defines information about a security association (SA) that a miniport driver should add to a NIC.
old-location: netvista\ipsec_offload_v2_add_sa_ex.htm
old-project: netvista
ms.assetid: ecb2ae2e-d57d-4192-965b-2ac9b16debf3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PIPSEC_OFFLOAD_V2_ADD_SA_EX, IPSEC_OFFLOAD_V2_ADD_SA_EX, IPSEC_OFFLOAD_V2_ADD_SA_EX structure [Network Drivers Starting with Windows Vista], PIPSEC_OFFLOAD_V2_ADD_SA_EX, PIPSEC_OFFLOAD_V2_ADD_SA_EX structure pointer [Network Drivers Starting with Windows Vista], _IPSEC_OFFLOAD_V2_ADD_SA_EX, ndis/IPSEC_OFFLOAD_V2_ADD_SA_EX, ndis/PIPSEC_OFFLOAD_V2_ADD_SA_EX, netvista.ipsec_offload_v2_add_sa_ex"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
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
req.irql: See Remarks section
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	IPSEC_OFFLOAD_V2_ADD_SA_EX
product: Windows
targetos: Windows
req.typenames: IPSEC_OFFLOAD_V2_ADD_SA_EX, *PIPSEC_OFFLOAD_V2_ADD_SA_EX, IPSEC_OFFLOAD_V2_ADD_SA_EX, *PIPSEC_OFFLOAD_V2_ADD_SA_EX
---

# _IPSEC_OFFLOAD_V2_ADD_SA_EX structure


## -description


<p class="CCE_Message">[The IPsec Task Offload feature is deprecated and should not be used.]

The IPSEC_OFFLOAD_V2_ADD_SA_EX structure defines information about a security association (SA) that a
  miniport driver should add to a NIC.


## -syntax


````
typedef struct _IPSEC_OFFLOAD_V2_ADD_SA_EX {
  NDIS_OBJECT_HEADER                    Header;
  ULONG                                 NumExtHdrs;
  ULONG                                 Flags;
  union {
    struct {
      IPAddr SrcAddr;
      IPAddr DestAddr;
    } IPv4Endpoints;
    struct {
      UCHAR SrcAddr[16];
      UCHAR DestAddr[16];
    } IPv6Endpoints;
  };
  NDIS_HANDLE                           OffloadHandle;
  ULONG                                 UdpEspEncapsulation;
  IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION SecAssoc[IPSEC_OFFLOAD_V2_MAX_EXTENSION_HEADERS];
  ULONG                                 KeyLength;
  ULONG                                 KeyOffset;
  NDIS_SWITCH_PORT_ID                   SourceSwitchPortId;
  USHORT                                VlanId;
} IPSEC_OFFLOAD_V2_ADD_SA_EX, *PIPSEC_OFFLOAD_V2_ADD_SA_EX;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     IPSEC_OFFLOAD_V2_ADD_SA_EX structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_IPSEC_OFFLOAD_V2_ADD_SA_EX_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_IPSEC_OFFLOAD_V2_ADD_SA_EX_REVISION_1.


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
     
     
     <a href="https://msdn.microsoft.com/library/windows/hardware/hh451937">OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA_EX</a> request. The TCP/IP transport must specify this handle in the
     
     <a href="..\ndis\ns-ndis-_ndis_ipsec_offload_v2_net_buffer_list_info.md">
     NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO</a> or 
     <a href="..\ndis\ns-ndis-_ndis_ipsec_offload_v2_tunnel_net_buffer_list_info.md">
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
     <a href="..\ndis\ns-ndis-_ipsec_offload_v2_security_association.md">
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
     <b>KeyOffset</b>.


### -field KeyOffset

The offset, in bytes, from the beginning of the IPSEC_OFFLOAD_V2_ADD_SA_EX structure to the beginning of a variable-length array that contains keys for the SA that is specified at 
     <b>SecAssoc</b>. If both an encryption algorithm and an authentication algorithm are specified by the 
     <b>EncryptionAlgorithm</b> and 
     <b>AuthenticationAlgorithm</b> members of an 
     <a href="..\ndis\ns-ndis-_ipsec_offload_v2_security_association.md">
     IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION</a> structure, the buffer at 
     <b>KeyOffset</b> contains key information for one followed by the other. The beginning and the length of
     the key are specified by the 
     <a href="..\ndis\ns-ndis-_ipsec_offload_v2_algorithm_info.md">
   IPSEC_OFFLOAD_V2_ALGORITHM_INFO</a> structure's <b>KeyOffsetBytes</b> and 
     <b>KeyLength</b> members, respectively.


### -field SourceSwitchPortId

Reserved.


### -field VlanId

Reserved.


## -remarks



The IPSEC_OFFLOAD_V2_ADD_SA_EX structure specifies a security SA that should be added. The IPSEC_OFFLOAD_V2_ADD_SA_EX structure is
    used with the 
    
    <a href="https://msdn.microsoft.com/library/windows/hardware/hh451937">OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA_EX</a> OID.

The IPSEC_OFFLOAD_V2_ADD_SA_EX structure specifies the source and destination, as well as the IP
    protocols, to which the SA applies. This filter pertains to a transport-mode connection--that is, an
    end-to-end connection between two hosts. If the specified connection is made through a tunnel, the source
    and destination addresses of the tunnel are specified.

If a member is set to zero, that parameter is not used to filter packets for the specified SA. For
    example, if 
    <b>SrcAddr</b> is set to zero, the specified SA can apply to a packet that contains any source address.
    If all of the filter parameters are set to zero, the specified SA applies to any source host that is
    sending any type of packet to any destination host.

This structure is nearly identical to the previous version, 
    <a href="..\ndis\ns-ndis-_ipsec_offload_v2_add_sa.md">IPSEC_OFFLOAD_V2_ADD_SA</a>. The <b>Next</b> and <b>KeyData</b> members have been removed. The <b>KeyOffset</b>, <b>SourceSwitchPortId</b> and <b>VlanId</b> members have been added.




## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-add-sa">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA_EX</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-delete-sa">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_DELETE_SA</a>



<a href="..\ndis\ns-ndis-_ipsec_offload_v2_security_association.md">
   IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION</a>



<a href="..\ndis\ns-ndis-_ndis_ipsec_offload_v2_net_buffer_list_info.md">
   NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO</a>



<a href="..\ndis\ns-ndis-_ipsec_offload_v2_add_sa.md">IPSEC_OFFLOAD_V2_ADD_SA</a>



<a href="..\ndis\ns-ndis-_ndis_ipsec_offload_v2_tunnel_net_buffer_list_info.md">
   NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO</a>



<a href="..\ndis\ns-ndis-_ipsec_offload_v2_algorithm_info.md">
   IPSEC_OFFLOAD_V2_ALGORITHM_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20IPSEC_OFFLOAD_V2_ADD_SA_EX structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

