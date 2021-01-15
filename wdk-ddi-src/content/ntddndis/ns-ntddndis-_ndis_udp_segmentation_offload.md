---
UID: NS:ntddndis._NDIS_UDP_SEGMENTATION_OFFLOAD
title: _NDIS_UDP_SEGMENTATION_OFFLOAD (ntddndis.h)
description: Specifies a buffer comprised of one or more NET_PACKET or NET_FRAGMENT structures.
tech.root: netvista
ms.date: 02/27/2020
ms.topic: struct
ms.keywords: _NDIS_UDP_SEGMENTATION_OFFLOAD, NDIS_UDP_SEGMENTATION_OFFLOAD, *PNDIS_UDP_SEGMENTATION_OFFLOAD,
req.header: ntddndis.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1912
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.alt-api: 
req.alt-loc: 
req.typenames: NDIS_UDP_SEGMENTATION_OFFLOAD
targetos: Windows
f1_keywords:
 - _NDIS_UDP_SEGMENTATION_OFFLOAD
 - ntddndis/_NDIS_UDP_SEGMENTATION_OFFLOAD
 - PNDIS_UDP_SEGMENTATION_OFFLOAD
 - ntddndis/PNDIS_UDP_SEGMENTATION_OFFLOAD
 - NDIS_UDP_SEGMENTATION_OFFLOAD
 - ntddndis/NDIS_UDP_SEGMENTATION_OFFLOAD
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - _NDIS_UDP_SEGMENTATION_OFFLOAD
 - PNDIS_UDP_SEGMENTATION_OFFLOAD
 - NDIS_UDP_SEGMENTATION_OFFLOAD
product:
 - Windows
---

# _NDIS_UDP_SEGMENTATION_OFFLOAD structure


## -description

The **NDIS_UDP_SEGMENTATION_OFFLOAD** structure provides UDP Segmentation Offload (USO) information in the [**NDIS_OFFLOAD**](../ntddndis/ns-ntddndis-_ndis_offload.md) structure.

## -struct-fields

### -field IPv4

A structure within **NDIS_UDP_SEGMENTATION_OFFLOAD** that specifies IPv4 information, containing the following members:

### -field IPv4.Encapsulation

Encapsulation settings for IPv4. For more information about this member, see the following Remarks section.

### -field IPv4.MaxOffLoadSize

The maximum bytes of user data that the transport can pass to the miniport driver in a single packet. The transport will not pass a packet to the miniport driver that contains more user data bytes than **MaxOffLoadSize** specifies. If such a packet must be transmitted, the transport itself segments the packet into smaller packets.

### -field IPv4.MinSegmentCount

The minimum number of segments that a large UDP packet must be divisible by before the transport can offload it to the hardware for segmentation. The transport will not offload a large packet to the miniport driver for segmentation unless the miniport driver can create at least as many segments as **MinSegmentCount** specifies from the packet. If a large UDP packet does not meet the minimum-segment requirement, the TCP/IP transport itself segments the packet into smaller packets.

### -field IPv4.SubMssFinalSegmentSupported

A ULONG value that specifies whether all segments that a miniport driver derives from a large UDP packet must be the same maximum segment size (MSS) or not. If the miniport driver does not set the **SubMssFinalSegmentSupported** capability, then each large UDP packet offloaded by the transport must have **Length % MSS == 0**. That is, the large packet is divisible into **N** packets with each packet segment containing exactly **MSS** user bytes. If the miniport driver sets the **SubMssFinalSegmentSupported** capability, then this packet length divisibility condition on the transport does not apply. In other words, the final segment can be less than **MSS**.

The driver should set the value of **SubMssFinalSegmentSupported** to **NDIS_OFFLOAD_SUPPORTED** if the miniport is capable of segmenting UDP sends where the total length of the large packet has a non-zero remainder when divided by **MSS**. When miniport driver support is indicated via this flag, the protocol driver is permitted to issue large UDP sends where the UDP payload length of the final segmented packet is less than **MSS**.

For more information, see [UDP Segmentation Offload (USO)](/windows-hardware/drivers/network/udp-segmentation-offload-uso-).

### -field IPv4.Reserved

Reserved. Miniport drivers must not read or write to this field.

### -field IPv6

A structure within **NDIS_UDP_SEGMENTATION_OFFLOAD** that specifies IPv6 information, containing the following members:

### -field IPv6.Encapsulation

Encapsulation settings for IPv6. For more information about this member, see the following Remarks section.

### -field IPv6.MaxOffLoadSize

The maximum bytes of user data that the transport can pass to the miniport driver in a single packet. The transport will not pass a packet to the miniport driver that contains more user data bytes than **MaxOffLoadSize** specifies. If such a packet must be transmitted, the transport itself segments the packet into smaller packets.

### -field IPv6.MinSegmentCount

The minimum number of segments that a large UDP packet must be divisible by before the transport can offload it to the hardware for segmentation. The transport will not offload a large packet to the miniport driver for segmentation unless the miniport driver can create at least as many segments as **MinSegmentCount** specifies from the packet. If a large UDP packet does not meet the minimum-segment requirement, the TCP/IP transport itself segments the packet into smaller packets.

### -field IPv6.SubMssFinalSegmentSupported

A ULONG value that specifies whether all segments that a miniport driver derives from a large UDP packet must be the same maximum segment size (MSS) or not. If the miniport driver does not set the **SubMssFinalSegmentSupported** capability, then each large UDP packet offloaded by the transport must have **Length % MSS == 0**. That is, the large packet is divisible into **N** packets with each packet segment containing exactly **MSS** user bytes. If the miniport driver sets the **SubMssFinalSegmentSupported** capability, then this packet length divisibility condition on the transport does not apply. In other words, the final segment can be less than **MSS**.

The driver should set the value of **SubMssFinalSegmentSupported** to **NDIS_OFFLOAD_SUPPORTED** if the miniport is capable of segmenting UDP sends where the total length of the large packet has a non-zero remainder when divided by **MSS**. When miniport driver support is indicated via this flag, the protocol driver is permitted to issue large UDP sends where the UDP payload length of the final segmented packet is less than **MSS**.

For more information, see [UDP Segmentation Offload (USO)](/windows-hardware/drivers/network/udp-segmentation-offload-uso-).

### -field IPv6.Reserved1

Reserved. Miniport drivers must not read or write to this field.

### -field IPv6.IpExtensionHeadersSupported

A ULONG value that a miniport driver sets to indicate that the miniport adapter can segment a large UDP packet whose IP header contains IPv6 extension headers.

### -field IPv6.Reserved2

Reserved. Miniport drivers must not read or write to this field.

## -remarks

Miniport drivers should set the values of this structure's fields and encapsulation requirements similarly to the [**NDIS_TCP_LARGE_SEND_OFFLOAD_V2**](../ntddndis/ns-ntddndis-_ndis_tcp_large_send_offload_v2.md) structure.

The **NDIS_UDP_SEGMENTATION_OFFLOAD** structure is used in the **UdpSegmentation** member of the [**NDIS_OFFLOAD**](../ntddndis/ns-ntddndis-_ndis_offload.md) structure. **NDIS_UDP_SEGMENTATION_OFFLOAD** specifies current or supported services that a miniport adapter provides for segmenting large UDP packets into smaller packets.

[**NDIS_OFFLOAD**](/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_offload) is used in the [**NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES**](/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_offload_attributes) structure, [**NDIS_BIND_PARAMETERS**](/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_bind_parameters) structure, [**NDIS_FILTER_ATTACH_PARAMETERS**](/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_filter_attach_parameters) structure, [OID_TCP_OFFLOAD_CURRENT_CONFIG](/windows-hardware/drivers/network/oid-tcp-offload-current-config) OID, and the [NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG](/windows-hardware/drivers/network/ndis-status-task-offload-current-config) status indication.

For  [OID_TCP_OFFLOAD_CURRENT_CONFIG](/windows-hardware/drivers/network/oid-tcp-offload-current-config), the [**NDIS_OFFLOAD**](/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_offload) structure specifies the task offload capabilities that a miniport adapter supports. If the current offloads capabilities change, a miniport driver reports the new capabilities in an [NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG](/windows-hardware/drivers/network/ndis-status-task-offload-current-config) status indication.

The **Encapsulation** members of **NDIS_UDP_SEGMENTATION_OFFLOAD** define the UDP encapsulation settings for the miniport adapter.

In response to an [OID_TCP_OFFLOAD_CURRENT_CONFIG](/windows-hardware/drivers/network/oid-tcp-offload-current-config) query request, NDIS provides a bitwise OR of the encapsulation flags, which indicate the supported encapsulation settings, in each of the  **Encapsulation** members. Miniport drivers must provide Ethernet encapsulation (NDIS_ENCAPSULATION_IEEE_802_3). The other types of encapsulation are optional.

For an [NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG](/windows-hardware/drivers/network/ndis-status-task-offload-current-config) status indication, the miniport driver provides a bitwise OR of the encapsulation flags, which indicate the current capabilities, in each of the **Encapsulation** members.

The following flags are defined for the **Encapsulation** members:

NDIS_ENCAPSULATION_NOT_SUPPORTED  
Specifies that no encapsulation offload is supported.

NDIS_ENCAPSULATION_NULL  
Specifies NULL encapsulation.

NDIS_ENCAPSULATION_IEEE_802_3  
Specifies IEEE 802.3 encapsulation.

NDIS_ENCAPSULATION_IEEE_802_3_P_AND_Q  
Specifies IEEE 802.3p and IEEE 802.3q encapsulation.

NDIS_ENCAPSULATION_IEEE_802_3_P_AND_Q_IN_OOB  
Specifies that IEEE 802.3p and IEEE 802.3q encapsulation settings are specified in the NetBufferListInfo member of each NET_BUFFER_LIST structure.

NDIS_ENCAPSULATION_IEEE_LLC_SNAP_ROUTED  
Specifies logical link control (LLC) encapsulation for routed protocols, as described in RFC 1483. This flag is also used to indicate Ethernet LLC/SNAP encapsulation.

## -see-also

[UDP Segmentation Offload (USO)](/windows-hardware/drivers/network/udp-segmentation-offload-uso-)

