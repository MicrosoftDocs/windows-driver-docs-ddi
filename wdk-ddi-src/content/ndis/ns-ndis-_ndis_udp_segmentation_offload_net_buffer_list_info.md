---
UID: NS:ndis._NDIS_UDP_SEGMENTATION_OFFLOAD_NET_BUFFER_LIST_INFO
title: _NDIS_UDP_SEGMENTATION_OFFLOAD_NET_BUFFER_LIST_INFO (ndis.h)
description: Specifies a buffer comprised of one or more NET_PACKET or NET_FRAGMENT structures.
tech.root: netvista
ms.assetid: C5EF1D54-AA43-4467-85B4-2134F9BA8E05
ms.date: 02/27/2030
ms.topic: struct
ms.keywords: _NDIS_UDP_SEGMENTATION_OFFLOAD_NET_BUFFER_LIST_INFO, NDIS_UDP_SEGMENTATION_OFFLOAD_NET_BUFFER_LIST_INFO, *PNDIS_UDP_SEGMENTATION_OFFLOAD_NET_BUFFER_LIST_INFO,
req.header: ndis.h
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
req.typenames: NDIS_UDP_SEGMENTATION_OFFLOAD_NET_BUFFER_LIST_INFO
targetos: Windows
f1_keywords:
 - _NDIS_UDP_SEGMENTATION_OFFLOAD_NET_BUFFER_LIST_INFO
 - ndis/_NDIS_UDP_SEGMENTATION_OFFLOAD_NET_BUFFER_LIST_INFO
 - PNDIS_UDP_SEGMENTATION_OFFLOAD_NET_BUFFER_LIST_INFO
 - ndis/PNDIS_UDP_SEGMENTATION_OFFLOAD_NET_BUFFER_LIST_INFO
 - NDIS_UDP_SEGMENTATION_OFFLOAD_NET_BUFFER_LIST_INFO
 - ndis/NDIS_UDP_SEGMENTATION_OFFLOAD_NET_BUFFER_LIST_INFO
topictype:
 - apiref
apitype:
 - HeaderDef
apilocation:
 - ndis.h
apiname:
 - NDIS_UDP_SEGMENTATION_OFFLOAD_NET_BUFFER_LIST_INFO
product:
 - Windows
---

# _NDIS_UDP_SEGMENTATION_OFFLOAD_NET_BUFFER_LIST_INFO structure


## -description

The **NDIS_UDP_SEGMENTATION_OFFLOAD_NET_BUFFER_LIST_INFO** structure specifies information that is used in offloading UDP Segmentation Offload (USO) tasks from the TCP/IP transport to a miniport adapter. The **NDIS_UDP_SEGMENTATION_OFFLOAD_NET_BUFFER_LIST_INFO** structure is part of the [**NET_BUFFER_LIST**](../ndis/ns-ndis-_net_buffer_list.md) OOB information.

## -struct-fields

### -field Transmit

A structure that contains individual bit fields for USO information.

### -field Transmit.MSS

The maximum segment size (MSS), in bytes, for each UDP segment. The TCP/IP transport writes this value before passing a large UDP packet to a miniport driver for segmentation.

### -field Transmit.UdpHeaderOffset

The offset, in bytes, of the UDP header from the beginning of the packet for UDP packets. Miniport drivers can use **UdpHeaderOffset** to determine the location of the UDP header so that they do not have to parse IP headers.

### -field Transmit.Reserved

Reserved. Miniport drivers must not read or write to this value.

### -field Transmit.IPVersion

The IP version of the packet. For IPv4 packets, **IPVersion** is set to NDIS_UDP_SEGMENTATION_OFFLOAD_IPV4. For IPv6 packets, **IPVersion** is set to NDIS_UDP_SEGMENTATION_OFFLOAD_IPV6.

### -field Value

A PVOID version of the USO information. Miniport drivers can use this member to access the raw information instead of the specific fields.

## -remarks

The **NDIS_UDP_SEGMENTATION_OFFLOAD_NET_BUFFER_LIST_INFO** structure is part of the information that is included in a [**NET_BUFFER_LIST**](../ndis/ns-ndis-_net_buffer_list.md) structure.

To set and get USO information, use the **UdpSegmentationOffloadInfo** index with the [**NET_BUFFER_LIST_INFO**](../ndis/nf-ndis-net_buffer_list_info.md) macro. **NET_BUFFER_LIST_INFO** returns a ULONG value (not a pointer to a ULONG value).

The TCP/IP transport updates the **MSS** and **UdpHeaderOffset** members of the **NDIS_UDP_SEGMENTATION_OFFLOAD_NET_BUFFER_LIST_INFO** structure before sending a large packet to a miniport driver.

>[!NOTE]
> Any **NET_BUFFER_LIST** structure that contains USO information also contains a single **NET_BUFFER** structure.

## -see-also

[UDP Segmentation Offload (USO)](/windows-hardware/drivers/network/udp-segmentation-offload-uso-)

[**NET_BUFFER_LIST**](../ndis/ns-ndis-_net_buffer_list.md)