---
UID: NE:ndis._NDIS_NET_BUFFER_LIST_INFO
title: "_NDIS_NET_BUFFER_LIST_INFO"
author: windows-driver-content
description: The NDIS_NET_BUFFER_LIST_INFO enumeration identifies information that is common to all NET_BUFFER structures in a NET_BUFFER_LIST structure.
old-location: netvista\ndis_net_buffer_list_info.htm
old-project: netvista
ms.assetid: 79327b2b-e97b-42dc-8d15-9d774c424cae
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_NET_BUFFER_LIST_INFO, ClassificationHandleNetBufferListInfo, IMReserved, IPsecOffloadV1NetBufferListInfo, IPsecOffloadV2HeaderNetBufferListInfo, IPsecOffloadV2NetBufferListInfo, IPsecOffloadV2TunnelNetBufferListInfo, Ieee8021QNetBufferListInfo, MaxNetBufferListInfo, MediaSpecificInformation, MediaSpecificInformationEx, NDIS_NET_BUFFER_LIST_INFO, NDIS_NET_BUFFER_LIST_INFO enumeration [Network Drivers Starting with Windows Vista], NblOriginalInterfaceIfIndex, NblReAuthWfpFlowContext, NetBufferListCancelId, NetBufferListCorrelationId, NetBufferListFilteringInfo, NetBufferListFrameType, NetBufferListHashInfo, NetBufferListHashValue, NetBufferListInfoReserved1, NetBufferListInfoReserved2, NetBufferListProtocolId, PNDIS_NET_BUFFER_LIST_INFO, PNDIS_NET_BUFFER_LIST_INFO enumeration pointer [Network Drivers Starting with Windows Vista], RscTcpTimestampDelta, SwitchForwardingDetail, SwitchForwardingReserved, TcpIpChecksumNetBufferListInfo, TcpLargeSendNetBufferListInfo, TcpOffloadBytesTransferred, TcpReceiveBytesTransferred, TcpReceiveNoPush, TcpRecvSegCoalesceInfo, TcpSendOffloadsSupplementalNetBufferListInfo, VirtualSubnetInfo, WfpNetBufferListInfo, _NDIS_NET_BUFFER_LIST_INFO, ndis/ClassificationHandleNetBufferListInfo, ndis/IMReserved, ndis/IPsecOffloadV1NetBufferListInfo, ndis/IPsecOffloadV2HeaderNetBufferListInfo, ndis/IPsecOffloadV2NetBufferListInfo, ndis/IPsecOffloadV2TunnelNetBufferListInfo, ndis/Ieee8021QNetBufferListInfo, ndis/MaxNetBufferListInfo, ndis/MediaSpecificInformation, ndis/MediaSpecificInformationEx, ndis/NDIS_NET_BUFFER_LIST_INFO, ndis/NblOriginalInterfaceIfIndex, ndis/NblReAuthWfpFlowContext, ndis/NetBufferListCancelId, ndis/NetBufferListCorrelationId, ndis/NetBufferListFilteringInfo, ndis/NetBufferListFrameType, ndis/NetBufferListHashInfo, ndis/NetBufferListHashValue, ndis/NetBufferListInfoReserved1, ndis/NetBufferListInfoReserved2, ndis/NetBufferListProtocolId, ndis/PNDIS_NET_BUFFER_LIST_INFO, ndis/RscTcpTimestampDelta, ndis/SwitchForwardingDetail, ndis/SwitchForwardingReserved, ndis/TcpIpChecksumNetBufferListInfo, ndis/TcpLargeSendNetBufferListInfo, ndis/TcpOffloadBytesTransferred, ndis/TcpReceiveBytesTransferred, ndis/TcpReceiveNoPush, ndis/TcpRecvSegCoalesceInfo, ndis/TcpSendOffloadsSupplementalNetBufferListInfo, ndis/VirtualSubnetInfo, ndis/WfpNetBufferListInfo, ndis_netbuf_enums_ref_c6cf9a86-d578-449f-bce0-850f8bbf04f3.xml, netvista.ndis_net_buffer_list_info"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_NET_BUFFER_LIST_INFO
product: Windows
targetos: Windows
req.typenames: NDIS_NET_BUFFER_LIST_INFO, *PNDIS_NET_BUFFER_LIST_INFO
---

# _NDIS_NET_BUFFER_LIST_INFO enumeration


## -description


The <b>NDIS_NET_BUFFER_LIST_INFO</b> enumeration identifies information that is common to all 
  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures in a 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.


## -syntax


````
typedef enum _NDIS_NET_BUFFER_LIST_INFO { 
  TcpIpChecksumNetBufferListInfo,
  TcpOffloadBytesTransferred                    = TcpIpChecksumNetBufferListInfo,
  IPsecOffloadV1NetBufferListInfo,
#if (NDIS_SUPPORT_NDIS61)
  IPsecOffloadV2NetBufferListInfo               = IPsecOffloadV1NetBufferListInfo,
#endif 
  TcpLargeSendNetBufferListInfo,
  TcpReceiveNoPush                              = TcpLargeSendNetBufferListInfo,
  ClassificationHandleNetBufferListInfo,
  Ieee8021QNetBufferListInfo,
  NetBufferListCancelId,
  MediaSpecificInformation,
  NetBufferListFrameType,
  NetBufferListProtocolId                       = NetBufferListFrameType,
  NetBufferListHashValue,
  NetBufferListHashInfo,
  WfpNetBufferListInfo,
#if (NDIS_SUPPORT_NDIS61)
  IPsecOffloadV2TunnelNetBufferListInfo,
  IPsecOffloadV2HeaderNetBufferListInfo,
#endif 
#if (NDIS_SUPPORT_NDIS620)
  NetBufferListCorrelationId,
  NetBufferListFilteringInfo,
  MediaSpecificInformationEx,
  NblOriginalInterfaceIfIndex,
  NblReAuthWfpFlowContext                       = NblOriginalInterfaceIfIndex,
  TcpReceiveBytesTransferred,
#if (NDIS_SUPPORT_NDIS630)
#if (_AMD64_) || (_ARM64_)
  SwitchForwardingReserved,
  SwitchForwardingDetail,
  VirtualSubnetInfo,
#endif 
  IMReserved,
  TcpRecvSegCoalesceInfo,
  RscTcpTimestampDelta,
  TcpSendOffloadsSupplementalNetBufferListInfo  = RscTcpTimestampDelta,
#endif 
#endif 
#if NDIS_WRAPPER == 1
  NetBufferListInfoReserved1,
  NetBufferListInfoReserved2,
#endif 
  MaxNetBufferListInfo
} NDIS_NET_BUFFER_LIST_INFO, *PNDIS_NET_BUFFER_LIST_INFO;
````


## -enum-fields




### -field TcpIpChecksumNetBufferListInfo

Identifies checksum information that is used in offloading checksum tasks from the TCP/IP protocol
     to a miniport driver. When 
     <b>TcpIpChecksumNetBufferListInfo</b> is specified, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro returns an 
     <a href="..\ndis\ns-ndis-_ndis_tcp_ip_checksum_net_buffer_list_info.md">
     NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO</a> structure. This structure contains a union that allows
     the checksum information to be accessed as a single <b>PVOID</b> value or as bit fields.


### -field TcpOffloadBytesTransferred

Identifies a <b>ULONG</b> value that is the number of data bytes that were transferred in a TCP chimney
     offload send, receive, or disconnect operation.


### -field IPsecOffloadV1NetBufferListInfo

Identifies Internet Protocol security (IPsec) information that is used in offloading IPsec tasks
     from the TCP/IP protocol to a miniport driver. When 
     <b>IPsecOffloadV1NetBufferListInfo</b> is specified, <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> returns an 
     <a href="..\ndis\ns-ndis-_ndis_ipsec_offload_v1_net_buffer_list_info.md">
     NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</a> structure.


### -field IPsecOffloadV2NetBufferListInfo

Specifies Internet protocol security offload version 2 (IPsecV2) information that is used in
      offloading IPsec tasks from the TCP/IP protocol to a miniport driver. When you specify 
      <b>IPsecOffloadV2NetBufferListInfo</b>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> returns an 
      <a href="..\ndis\ns-ndis-_ndis_ipsec_offload_v2_net_buffer_list_info.md">
      NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO</a> structure.


### -field TcpLargeSendNetBufferListInfo

Identifies information that is used in offloading the segmentation of a large TCP packet from the
     TCP/IP protocol to a miniport adapter for large send offload version 1 (LSOV1) and large send offload
     version 2 (LSOV2). When 
     <b>TcpLargeSendNetBufferListInfo</b> is specified, <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> returns an 
     <a href="..\ndis\ns-ndis-_ndis_tcp_large_send_offload_net_buffer_list_info.md">
     NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO</a> structure. This structure contains a union that
     enables the information to be accessed as a single PVOID value or as bit fields.
     

Before passing a large TCP packet to a miniport driver for segmentation, the TCP/IP protocol writes
     the values in the 
     <b>LsoV1Transmit</b> member of the <a href="..\ndis\ns-ndis-_ndis_tcp_large_send_offload_net_buffer_list_info.md">
     NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO</a> structure for LSOV1
     or the 
     <b>LsoV2Transmit</b> member for LSOV2. Before completing the send of a large TCP packet that it has
     segmented into smaller packets, a miniport driver writes the values in the 
     <b>LsoV1TransmitComplete</b> member of the <b>
     NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO</b> structure for
     LSOV1 or the 
     <b>LsoV2TransmitComplete</b> member for LSOV2. For LSOV1, the value that the miniport driver writes
     includes the total number of TCP payload bytes that the miniport driver sent in the packets that it
     segmented from the large TCP packet.


### -field TcpReceiveNoPush

Identifies a <b>Boolean</b> value that represents the push mode of a TCP chimney offload receive request.
     If <b>TRUE</b>, the receive request is in non-push mode. Otherwise, the receive request is in push mode.


### -field ClassificationHandleNetBufferListInfo

Reserved.


### -field Ieee8021QNetBufferListInfo

Identifies 802.1Q information about a packet. When 
     <b>Ieee8021QNetBufferListInfo</b> is specified, 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> returns the 
     <b>Value</b> member of an 
     <a href="..\ndis\ns-ndis-_ndis_net_buffer_list_8021q_info.md">
     NDIS_NET_BUFFER_LIST_8021Q_INFO</a> structure. This structure can specify 802.1p priority and VLAN
     identifier information. 802.1p priority information is used to establish packet priority in shared-media
     802 networks. Miniport drivers that support the 802.1Q tag in hardware must use the
     <b>
     NDIS_NET_BUFFER_LIST_8021Q_INFO</b> structure for transmit and receive operations.


### -field NetBufferListCancelId

Identifies a <b>ULONG_PTR</b> value that is a cancellation identifier for the 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. To cancel the
     pending transmission of a marked <b>NET_BUFFER_LIST</b> structure, a protocol driver passes the packet's
     cancellation identifier to 
     <a href="..\ndis\nf-ndis-ndiscancelsendnetbufferlists.md">
     NdisCancelSendNetBufferLists</a>. Drivers must call 
     <a href="..\ndis\nf-ndis-ndisgeneratepartialcancelid.md">
     NdisGeneratePartialCancelId</a> to obtain a value that the driver must use as the high-order byte of a
     cancellation identifier.


### -field MediaSpecificInformation

Identifies a PVOID value that is the address of a driver-allocated buffer. This buffer contains
     any media-specific out-of-band data that accompanies the 
     <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures that are associated with
     the <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. If a protocol driver allocated the out-of-band data, it configured the
     data for a send operation. If a miniport driver allocated the data, it configured the data for a receive
     indication.


### -field NetBufferListFrameType

Identifies a <b>USHORT</b> value that is the frame type of the received Ethernet packets.


### -field NetBufferListProtocolId

Identifies a <b>UCHAR</b> value that is a protocol identifier as one of the following values: 
     





#### NDIS_PROTOCOL_ID_DEFAULT

A default protocol driver identifier.



#### NDIS_PROTOCOL_ID_TCP_IP

The TCP/IP protocol.



#### NDIS_PROTOCOL_ID_IPX

The IPX protocol.



#### NDIS_PROTOCOL_ID_NBF

The NetBEUI protocol.


### -field NetBufferListHashValue

On the receive path, 
     <b>NetBufferListHashValue</b> identifies a <b>ULONG</b> value that is the RSS hash value that a NIC calculated,
     if any. 
     

On the transmit path, 
     <b>NetBufferListHashValue</b> identifies a <b>ULONG</b> value that is the RSS hash value that TCP/IP calculated,
     if any. In this case, all <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures in a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that TCP/IP submitted
     belong to the same UDP or TCP connection. Therefore, this hash value applies to all <b>NET_BUFFER</b>
     structures that are in the <b>NET_BUFFER_LIST</b> structure.

For more information, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/indicating-rss-receive-data">Indicating RSS Receive
     Data</a>.


### -field NetBufferListHashInfo

Identifies a <b>ULONG</b> value that is the RSS hash information, which includes the hash function and
     hash type. For more information, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/indicating-rss-receive-data">Indicating RSS Receive
     Data</a>.


### -field WfpNetBufferListInfo

Reserved for use by the Windows Filtering Platform (WFP). No drivers, including WFP callout
     drivers, can store information by using this value.


### -field IPsecOffloadV2TunnelNetBufferListInfo

Specifies IPsecV2 tunnel information that is used in offloading IPsec tasks from the TCP/IP protocol
      to a miniport driver. When you specify 
      <b>IPsecOffloadV2TunnelNetBufferListInfo</b>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> returns an 
      <a href="..\ndis\ns-ndis-_ndis_ipsec_offload_v2_tunnel_net_buffer_list_info.md">
      NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO</a> structure.


### -field IPsecOffloadV2HeaderNetBufferListInfo

Specifies IPsecV2 header information that is used in offloading IPsec tasks from the TCP/IP protocol
      to a miniport driver. When you specify <b>IPsecOffloadV2HeaderNetBufferListInfo</b>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> returns an 
      <a href="..\ndis\ns-ndis-_ndis_ipsec_offload_v2_header_net_buffer_list_info.md">
      NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO</a> structure.


### -field NetBufferListCorrelationId

Reserved.


### -field NetBufferListFilteringInfo

Specifies filtering information that is used in the virtual machine queue (VMQ) interface, the single root I/O virtualization (SR-IOV) interface, and NDIS packet coalescing. When you specify 
     <b>NetBufferListFilteringInfo</b>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> returns an 
     <a href="..\ndis\ns-ndis-_ndis_net_buffer_list_filtering_info.md">
     NDIS_NET_BUFFER_LIST_FILTERING_INFO</a> structure.

Starting with NDIS 6.20, receive indications made by miniport drivers that support VMQ, SR-IOV, or packet coalesing must include an <a href="..\ndis\ns-ndis-_ndis_net_buffer_list_filtering_info.md">NDIS_NET_BUFFER_LIST_FILTERING_INFO</a> structure. The miniport drivers must set the VMQ queue identifier in the 
     <b>QueueId</b> member of the <b>
     NDIS_NET_BUFFER_LIST_FILTERING_INFO</b> structure.  The driver also sets the <b>FilterId</b> member of the <b>NDIS_NET_BUFFER_LIST_FILTERING_INFO</b> structure to zero. 

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, the miniport driver that supports SR-IOV or packet coalescing must set the <b>QueueId</b> to <b>NDIS_DEFAULT_RECEIVE_QUEUE_ID</b> and the <b>FilterId</b> member to zero.</div>
<div> </div>

### -field MediaSpecificInformationEx

Identifies a pointer to a driver-allocated 
     <a href="..\ndis\ns-ndis-_ndis_nbl_media_specific_information_ex.md">
     NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX</a> structure. This structure identifies any media-specific
     out-of-band data that accompanies the <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures that are associated with the <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
     structure. NDIS 6.20 and later drivers should use the <b>
     NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX</b> structure
     to specify media specific information. Any driver in an NDIS driver stack can allocate and manage
     media-specific information.


### -field NblOriginalInterfaceIfIndex

Reserved.


### -field NblReAuthWfpFlowContext

Reserved.


### -field TcpReceiveBytesTransferred

Identifies a <b>ULONG</b> value that is the number of data bytes that were received by the host stack and
     filled in the receive request that is being processed as a TCP chimney offload receive operation.


### -field NrtNameResolutionId


### -field SwitchForwardingReserved

Reserved for NDIS.


### -field SwitchForwardingDetail

Identifies a pointer to a driver-allocated <a href="..\ndis\ns-ndis-_ndis_switch_forwarding_detail_net_buffer_list_info.md">NDIS_SWITCH_FORWARDING_DETAIL_NET_BUFFER_LIST_INFO</a> structure. This  structure specifies the information for forwarding a packet to one or more  ports of a Hyper-V extensible switch. The driver allocates this structure by calling <a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a> and frees the structure by calling <a href="https://msdn.microsoft.com/08AE3160-276F-4D1F-9D02-AD5AF38CDED2">FreeNetBufferListForwardingContext</a>.


### -field VirtualSubnetInfo

Identifies a pointer to a driver-allocated <a href="..\ndis\ns-ndis-_ndis_net_buffer_list_virtual_subnet_info.md">NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO</a> structure. 


### -field IMReserved

Reserved for NDIS.


### -field TcpRecvSegCoalesceInfo

Identifies a pointer to a driver-allocated <a href="..\ndis\ns-ndis-_ndis_rsc_nbl_info.md">NDIS_RSC_NBL_INFO</a> union containing receive segment coalescing (RSC) counter information. For more information, see the <a href="..\ndis\ns-ndis-_ndis_rsc_nbl_info.md">NDIS_RSC_NBL_INFO</a> documentation.


### -field RscTcpTimestampDelta

Identifies a pointer to a driver-allocated <a href="..\ndis\ns-ndis-_ndis_rsc_nbl_info.md">NDIS_RSC_NBL_INFO</a> union containing RSC timestamp information. For more information, see the <a href="..\ndis\ns-ndis-_ndis_rsc_nbl_info.md">NDIS_RSC_NBL_INFO</a> documentation.


### -field TcpSendOffloadsSupplementalNetBufferListInfo

Identifies a pointer to a driver-allocated <a href="..\ndis\ns-ndis-_ndis_tcp_send_offloads_supplemental_net_buffer_list_info.md">NDIS_TCP_SEND_OFFLOADS_SUPPLEMENTAL_NET_BUFFER_LIST_INFO</a> structure containing additional out-of-band information for encapsulated packets.


### -field GftOffloadInformation


### -field GftFlowEntryId


### -field NetBufferListInfoReserved3


### -field NetBufferListInfoReserved4


### -field NetBufferListInfoReserved1

Reserved for NDIS.


### -field NetBufferListInfoReserved2

Reserved for NDIS.


### -field MaxNetBufferListInfo

The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.




## -remarks



The <b>NDIS_NET_BUFFER_LIST_INFO</b> enumeration is used in the 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.

Use these enumeration values with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro to set and
    get values in the 
    <b>NetBufferListInfo</b> array in a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>.




## -see-also

<a href="..\ndis\ns-ndis-_ndis_ipsec_offload_v2_tunnel_net_buffer_list_info.md">
   NDIS_IPSEC_OFFLOAD_V2_TUNNEL_NET_BUFFER_LIST_INFO</a>



<a href="..\ndis\ns-ndis-_ndis_net_buffer_list_8021q_info.md">
   NDIS_NET_BUFFER_LIST_8021Q_INFO</a>



<a href="..\ndis\ns-ndis-_ndis_net_buffer_list_filtering_info.md">
   NDIS_NET_BUFFER_LIST_FILTERING_INFO</a>



<a href="..\ndis\ns-ndis-_ndis_tcp_ip_checksum_net_buffer_list_info.md">
   NDIS_TCP_IP_CHECKSUM_NET_BUFFER_LIST_INFO</a>



<a href="..\ndis\nf-ndis-ndisgeneratepartialcancelid.md">NdisGeneratePartialCancelId</a>



<a href="..\ndis\ns-ndis-_ndis_ipsec_offload_v1_net_buffer_list_info.md">
   NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</a>



<a href="..\ndis\ns-ndis-_ndis_net_buffer_list_virtual_subnet_info.md">NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO</a>



<a href="..\ndis\ns-ndis-_ndis_ipsec_offload_v2_net_buffer_list_info.md">
   NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO</a>



<a href="..\ndis\ns-ndis-_ndis_switch_forwarding_detail_net_buffer_list_info.md">NDIS_SWITCH_FORWARDING_DETAIL_NET_BUFFER_LIST_INFO</a>



<a href="..\ndis\nf-ndis-ndiscancelsendnetbufferlists.md">NdisCancelSendNetBufferLists</a>



<a href="..\ndis\ns-ndis-_ndis_nbl_media_specific_information_ex.md">
   NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX</a>



<a href="..\ndis\ns-ndis-_ndis_tcp_large_send_offload_net_buffer_list_info.md">
   NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



<a href="..\ndis\ns-ndis-_ndis_ipsec_offload_v2_header_net_buffer_list_info.md">
   NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NET_BUFFER_LIST_INFO enumeration%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

