---
UID: NS:ntddndis._OFFLOAD_IPSEC_ADD_SA
title: "_OFFLOAD_IPSEC_ADD_SA"
author: windows-driver-content
description: The OFFLOAD_IPSEC_ADD_SA structure contains information for each security association (SA) that a miniport driver adds to a NIC.
old-location: netvista\offload_ipsec_add_sa.htm
old-project: netvista
ms.assetid: 592d338c-8ab0-4163-bcfa-75c941b83c3d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *POFFLOAD_IPSEC_ADD_SA, ,, 216offload_12f95ec9-ed81-43cc-b90d-fe06600ec349.xml, A, C, D, E, F, I, L, O, OFFLOAD_IPSEC_ADD_SA, OFFLOAD_IPSEC_ADD_SA structure [Network Drivers Starting with Windows Vista], P, POFFLOAD_IPSEC_ADD_SA, POFFLOAD_IPSEC_ADD_SA structure pointer [Network Drivers Starting with Windows Vista], S, _, _OFFLOAD_IPSEC_ADD_SA, netvista.offload_ipsec_add_sa, ntddndis/OFFLOAD_IPSEC_ADD_SA, ntddndis/POFFLOAD_IPSEC_ADD_SA"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddndis.h
apiname:
-	OFFLOAD_IPSEC_ADD_SA
product: Windows
targetos: Windows
req.typenames: OFFLOAD_IPSEC_ADD_SA, *POFFLOAD_IPSEC_ADD_SA
---

# _OFFLOAD_IPSEC_ADD_SA structure


## -description


The OFFLOAD_IPSEC_ADD_SA structure contains information for each security association (SA) that a
  miniport driver adds to a NIC.


## -syntax


````
typedef struct _OFFLOAD_IPSEC_ADD_SA {
  IPAddr                       SrcAddr;
  IPMask                       SrcMask;
  IPAddr                       DestAddr;
  IPMask                       DestMask;
  ULONG                        Protocol;
  USHORT                       SrcPort;
  USHORT                       DestPort;
  IPAddr                       SrcTunnelAddr;
  IPAddr                       DestTunnelAddr;
  USHORT                       Flags;
  SHORT                        NumSAs;
  OFFLOAD_SECURITY_ASSOCIATION SecAssoc[OFFLOAD_MAX_SAS];
  HANDLE                       OffloadHandle;
  ULONG                        KeyLen;
  UCHAR                        KeyMat[1];
} OFFLOAD_IPSEC_ADD_SA, *POFFLOAD_IPSEC_ADD_SA;
````


## -struct-fields




### -field SrcAddr

The IP address of the source host (the host sending the packets).


### -field SrcMask

The subnet mask for the source IP address.


### -field DestAddr

The IP address of the destination host (the host receiving the packets).


### -field DestMask

The subnet mask for the destination IP address.


### -field Protocol

The IP protocol. You can specify any combination of IP protocol types (such as TCP, UDP, or ICMP).
     The encoding of 
     <b>Protocol</b> is identical to that of the Protocol field in an IP header. If 
     <b>Protocol</b> is set to zero, the SA applies to any IP protocol.


### -field SrcPort

A source TCP or UDP port. If 
     <b>SrcPort</b> is set to zero, the SA applies to any source TCP/UDP port.


### -field DestPort

A destination TCP or UDP port. If 
     <b>DestPort</b> is set to zero, the SA applies to any source TCP/UDP port.


### -field SrcTunnelAddr

The IP address for the source endpoint, such as a connector, of a tunnel. The miniport driver uses
     
     <b>SrcTunnelAddr</b> as the source address for the tunnel IP header of packets that are sent on the SA. 
     <b>SrcTunnelAddr</b> is specified only for an SA that applies to the tunnel portion of a packet. 
     <b>SrcTunnelAddr</b> is set to zero for an SA that applies to the transport portion of a packet.


### -field DestTunnelAddr

The IP address for the destination endpoint, such as a connector, of a tunnel. The miniport driver
     uses 
     <b>DestTunnelAddr</b> as the destination address for the tunnel IP header of packets sent on the SA. 
     <b>DestTunnelAddr</b> is specified only for an SA that applies to the tunnel portion of a packet. 
     <b>DestTunnelAddr</b> is set to zero for an SA that applies to the transport portion of a packet.


### -field Flags

A bitmask that indicates whether the SA that is being added is an inbound or outbound SA as
     follows:
     





#### OFFLOAD_INBOUND_SA

Specifies an inbound SA.



#### OFFLOAD_OUTBOUND_SA

Specifies an outbound SA.


### -field NumSAs

The number of elements in the 
     <b>SecAssoc</b> array. Each element in the array is an 
     <a href="..\ntddndis\ns-ntddndis-_offload_security_association.md">
     OFFLOAD_SECURITY_ASSOCIATION</a> structure.


### -field SecAssoc

A variable-length array that contains the information about the Internet Protocol security (IPsec)
     operations (AH or ESP) for the SA. The information for each IPsec operations is formatted as an
     OFFLOAD_SECURITY_ASSOCIATION structure.
     

The TCP/IP transport specifies one or two OFFLOAD_SECURITY_ASSOCIATION structures in the buffer at 
     <b>SecAssoc</b> . Each OFFLOAD_SECURITY_ASSOCIATION structure indicates the type of
     operation--authentication or encryption/decryption--for which the SA specified in the structure is to be
     used. The order of the OFFLOAD_SECURITY_ASSOCIATION structures in the array indicates the order in which
     the miniport driver should perform the operations for each SA. Only one combination of operations is
     supported: encryption/decryption (ESP) followed by authentication (AH).


### -field OffloadHandle

The handle to the newly created SA. The miniport driver supplies this handle before completing the
     
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569808">OID_TCP_TASK_IPSEC_ADD_SA</a> request.
     The TCP/IP transport must specify this handle in the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff557028">NDIS_IPSEC_PACKET_INFO</a> structure before
     passing a send packet to the miniport driver. The TCP/IP transport must also specify this handle when
     deleting the SA with an 
     <a href="https://msdn.microsoft.com/en-us/library/gg155485.aspx">
     OID_TCP_TASK_IPSEC_DELETE_SA</a> request.


### -field KeyLen

The length, in bytes, of the buffer at 
     <b>KeyMat</b> .


### -field KeyMat

A variable-length array that contains keys for the SAs specified at 
     <b>SecAssoc</b> . If both a confidentiality (encryption/decryption) algorithm and an integrity
     (authentication) algorithm are specified by the 
     <b>ConfAlgo</b> and 
     <b>IntegrityAlgo</b> members of an 
     <a href="..\ntddndis\ns-ntddndis-_offload_security_association.md">
     OFFLOAD_SECURITY_ASSOCIATION</a> structure, the buffer at 
     <b>KeyMat</b> contains key information for the confirmation algorithm first, followed immediately by key
     information for the integrity algorithm.
     

The length of each key in the buffer at 
     <b>KeyMat</b> is specified by 
     <b>algoKeylen</b> in the 
     <a href="..\ntddndis\ns-ntddndis-_offload_algo_info.md">OFFLOAD_ALGO_INFO</a> structure that
     specifies the confidentiality or integrity algorithm. (An OFFLOAD_ALGO_INFO structure is a member of an
     OFFLOAD_SECURITY_ASSOCIATION structure.)


## -remarks



The OFFLOAD_IPSEC_ADD_SA structure is used in the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569808">OID_TCP_TASK_IPSEC_ADD_SA</a> OID.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_offload_algo_info.md">OFFLOAD_ALGO_INFO</a>



<a href="..\ntddndis\ns-ntddndis-_offload_security_association.md">OFFLOAD_SECURITY_ASSOCIATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569808">OID_TCP_TASK_IPSEC_ADD_SA</a>



<a href="https://msdn.microsoft.com/en-us/library/gg155485.aspx">OID_TCP_TASK_IPSEC_DELETE_SA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557028">NDIS_IPSEC_PACKET_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20OFFLOAD_IPSEC_ADD_SA structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

