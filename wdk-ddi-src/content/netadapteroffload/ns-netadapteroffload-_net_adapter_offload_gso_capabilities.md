---
UID: NS:netadapteroffload._NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES
title: _NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES (netadapteroffload.h)
description: The NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES structure describes a network interface card (NIC)'s capabilities for generic send offload (GSO).
tech.root: netvista
ms.assetid: 73c5e8ec-69ef-4c3d-9864-c728f86b3551
ms.date: 01/17/2019
keywords: ["_NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES structure"]
f1_keywords:
 - "netadapteroffload/_NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES"
ms.keywords: _NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES, NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES, *PNET_ADAPTER_OFFLOAD_GSO_CAPABILITIES, 
req.header: netadapteroffload.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.29
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES, *PNET_ADAPTER_OFFLOAD_GSO_CAPABILITIES
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- netadapteroffload.h
api_name: 
- _NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# _NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES structure

## -description



The **NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES** structure describes a network interface card (NIC)'s capabilities for generic send offload (GSO).

## -struct-fields

### -field Size

The size of this structure, in bytes.
 
### -field Layer3Flags

Flags specifying the layer 3 protocols and variations contained in packets that the NIC can successfully perform generic send offload (GSO) on. 

The flags should be a combination of:

| Flag | Description |
| --- | --- |
| NetAdapterOffloadFlagIPv4WithoutOptions | Set if the NIC is capable of performing GSO on IPv4 packets without options |
| NetAdapterOffloadFlagIPv4WithOptions | Set if the NIC is capable of performing GSO on IPv4 packets with options |
| NetAdapterOffloadFlagIPv6WithoutExtensions | Set if the NIC is capable of performing GSO on IPv6 packets without extensions |
| NetAdapterOffloadFlagIPv6WithExtensions | Set if the NIC is capable of performing GSO on IPv6 packets with extensions |


### -field Layer4Flags

Flags specifying the layer 4 protocols and variations contained in packets that the NIC can successfully perform generic send offload (GSO) on. The `NetAdapterOffloadFlagTcpWithoutOptions` flag must be set if LSO is supported by the NIC. The `NetAdapterOffloadFlagUdp` flag must be set if USO is supported by the NIC.

The flags should be a combination of:

| Flag | Description |
| --- | --- |
| NetAdapterOffloadFlagTcpWithoutOptions | Set if the NIC is capable of performing LSO on TCP packets without options |
| NetAdapterOffloadFlagTcpWithOptions | Set if the NIC is capable of performing LSO on TCP packets with options |
| NetAdapterOffloadFlagUdp | Set if the NIC is capable of performing USO on UDP packets |

### -field Layer4OffsetLimit

The maximum layer 4 header offset that the NIC supports in bytes.

### -field MaximumOffloadSize

The maximum bytes of user data that the transport can pass to the NIC driver in a single packet.
 
### -field MinimumSegmentCount
 
The minimum number of segments by which a large TCP/UDP packet must be divisible before the transport can offload it to the hardware for segmentation.

### -field EvtAdapterOffloadSetGso

A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_OFFLOAD_SET_GSO*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_gso.md) callback function.

## -remarks

Call [**NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES_INIT**](../netadapteroffload/nf-netadapteroffload-net_adapter_offload_gso_capabilities_init.md) to initialize this structure. An initialized **NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES** structure is passed as a parameter to [**NetAdapterOffloadSetGsoCapabilities**](../netadapteroffload/nf-netadapteroffload-netadapteroffloadsetgsocapabilities.md).

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[**NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES_INIT**](../netadapteroffload/nf-netadapteroffload-net_adapter_offload_gso_capabilities_init.md)

[**NetAdapterOffloadSetGsoCapabilities**](../netadapteroffload/nf-netadapteroffload-netadapteroffloadsetgsocapabilities.md)
