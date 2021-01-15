---
UID: NS:ntddndis._NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2
title: _NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2 (ntddndis.h)
description: The NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2 structure contains the offload support state for VXLAN task offload. This structure is used in the EncapsulatedPacketTaskOffloadVxlan member of the NDIS_OFFLOAD structure.
tech.root: netvista
ms.date: 05/22/2018
keywords: ["NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2 structure"]
ms.keywords: _NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2, NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2, *PNDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2,
req.header: ntddndis.h
req.include-header: ndis.h
req.target-type: 
req.target-min-winverclnt: NDIS 6.50
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2, *PNDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2
 - ntddndis/_NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2
 - PNDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2
 - ntddndis/PNDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2
 - NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2
 - ntddndis/NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - _NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2
 - PNDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2
 - NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2
---

# _NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2 structure


## -description

The **NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2** structure contains packet encapsulation information for Virtual Extensible LAN (VXLAN) task offload. VXLAN is similar to [NVGRE task offload](/windows-hardware/drivers/network/network-virtualization-using-generic-routing-encapsulation--nvgre--task-offload), but with a different protocol.

This structure is used in the **EncapsulatedPacketTaskOffloadVxlan** member of the [**NDIS_OFFLOAD**](ns-ntddndis-_ndis_offload.md) structure in NDIS 6.70 and later.

## -struct-fields

### -field TransmitChecksumOffloadSupported

Task offload settings for transmit checksum.

### -field ReceiveChecksumOffloadSupported

Task offload settings for receive checksum.

### -field LsoV2Supported

Task offload settings for large send offload version 2 (LSOv2).

### -field RssSupported

Task offload settings for receive side scaling (RSS).

### -field VmqSupported

Task offload settings for virtual machine queue (VMQ).

### -field Reserved

Reserved for system use.

### -field MaxHeaderSizeSupported

This member should be set to the maximum header size from the beginning of the packet to the beginning of the inner TCP or UDP payload (the last byte of TCP or UDP inner header) that the NIC must support for all of these task offloads. The protocol driver is expected to not offload processing of a packet whose combined encapsulation headers exceed this size. 

> [!TIP]
> 256 bytes is a good default value that should cover all possible cases.

### -field EncapsulationProtocolInfo

A union that contains the **VxlanInfo** member and the **Value** member.

### -field EncapsulationProtocolInfo.VxlanInfo

A struct that contains the **VxlanUDPPortNumber** member and the **VxlanUDPPortNumberConfigurable** member.

### -field EncapsulationProtocolInfo.VxlanInfo.VxlanUDPPortNumber

The port number to use for the VXLAN UDP destination port.

### -field EncapsulationProtocolInfo.VxlanInfo.VxlanUDPPortNumberConfigurable

Describes whether the UDP port number is configurable.

### -field EncapsulationProtocolInfo.Value

The UDP checksum value for this packet.

### -field _ENCAPSULATION_PROTOCOL_INFO

### -field Reserved1

Reserved for system use.

### -field Reserved2

 
Reserved for system use.

## -remarks

In the initial capability advertisement and in [NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG](/windows-hardware/drivers/network/ndis-status-task-offload-current-config) and [NDIS_STATUS_TASK_OFFLOAD_HARDWARE_CAPABILITIES](/windows-hardware/drivers/network/ndis-status-task-offload-hardware-capabilities) status indications, the **TransmitChecksumOffloadSupported**, **ReceiveChecksumOffloadSupported**, **LsoV2Supported**, **RssSupported**, and **VmqSupported** members can be set to a bitwise OR of the following flags:

| Term | Description |
| --- | --- |
| NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_NOT_SUPPORTED | Specifies that the miniport adapter does not support the corresponding task offload feature that the member specifies. |
| NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_INNER_IPV4 | Specifies that the miniport adapter supports the corresponding task offload feature that the member specifies where the inner IP header of an encapsulated packet is IPv4. |
| NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_OUTER_IPV4 | Specifies that the miniport adapter supports the corresponding task offload feature that the member specifies where the outer IP header of an encapsulated packet is IPv4. |
| NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_INNER_IPV6 | Specifies that the miniport adapter supports the corresponding task offload feature that the member specifies where the inner IP header of an encapsulated packet is IPv6. |
| NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_OUTER_IPV6 | Specifies that the miniport adapter supports the corresponding task offload feature that the member specifies where the outer IP header of an encapsulated packet is IPv6. |

As an example, if a miniport adapter and driver only support an IPv6 header as outer IP header but not as inner IP header, it will set **TransmitChecksumOffloadSupported**, **ReceiveChecksumOffloadSupported**, **LsoV2Supported**, **RssSupported**, and **VmqSupported** to the value of the bitwise OR of NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_INNER_IPV4, NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_OUTER_IPV4 and NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_OUTER_IPV6.

Regarding IP options and TCP options, the following assumption was made for encapsulated packets:

- If the NIC specifies **IpOptions** and **TcpOptions** support in normal checksum offload and LSOv2 advertisement, it must support the option processing for encapsulated packets if Network Virtualization using VXLAN task offload is supported. This means it will support both inner and outer IP options and TCP options inside the encapsulated packets. There is no separate capability advertisement for these specific to only VXLAN task offload.

It is possible for a protocol driver to offload "mixed mode" packets which means packets in which the inner and outer IP header versions are different. For example, a packet could have outer IP header as IPv6 and the inner IP header as IPv4.

For more information about VXLAN, see [RFC 7348](https://tools.ietf.org/html/rfc7348).

## -see-also

[**NDIS_OFFLOAD**](ns-ntddndis-_ndis_offload.md)

