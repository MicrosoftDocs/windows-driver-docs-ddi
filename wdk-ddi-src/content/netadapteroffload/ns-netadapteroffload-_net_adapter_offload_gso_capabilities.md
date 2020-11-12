---
UID: NS:netadapteroffload._NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES
title: _NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES (netadapteroffload.h)
description: The NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES structure describes a network interface card (NIC)'s capabilities for generic send offload (GSO).
tech.root: netvista
ms.assetid: 
ms.date: 10/09/2020
keywords: ["_NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES structure"]
f1_keywords:
 - "netadapteroffload/_NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES"
ms.keywords: _NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES, NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES, *PNET_ADAPTER_OFFLOAD_GSO_CAPABILITIES, 
req.header: netadapteroffload.h
req.include-header: netadaptercx.h
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
ms.custom: Fe
---

# _NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES structure

## -description

> [!WARNING]
> Some information in this topic relates to pre-released product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 2004.
>
> Currently, NetAdapterCx client drivers cannot be certified.

The **NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES** structure describes a network interface card (NIC)'s capabilities for [Generic Segmentation Offload (GSO)](/windows-hardware/drivers/netcx/gso-offload).

## -struct-fields

### -field Size

The size of this structure, in bytes.
 
### -field Layer3Flags

Flags specifying the layer 3 protocol variations that the NIC can successfully perform GSO on.

The flags should be a combination of:

| Flag | Description |
| --- | --- |
| NetAdapterOffloadLayer3FlagIPv4NoOptions | Set if the NIC is capable of performing GSO on IPv4 packets without options |
| NetAdapterOffloadLayer3FlagIPv4WithOptions | Set if the NIC is capable of performing GSO on IPv4 packets with options |
| NetAdapterOffloadLayer3FlagIPv6NoExtensions | Set if the NIC is capable of performing GSO on IPv6 packets without extensions |
| NetAdapterOffloadLayer3FlagIPv6WithExtensions | Set if the NIC is capable of performing GSO on IPv6 packets with extensions |


### -field Layer4Flags

Flags specifying the layer 4 protocol variations that the NIC can successfully perform GSO on. The `NetAdapterOffloadLayer4FlagTcpNoOptions` flag must be set if the NIC supports LSO. The `NetAdapterOffloadLayer4FlagUdp` flag must be set if the NIC supports USO.

The flags should be a combination of:

| Flag | Description |
| --- | --- |
| NetAdapterOffloadLayer4FlagTcpNoOptions | Set if the NIC is capable of performing LSO on TCP packets without options |
| NetAdapterOffloadLayer4FlagTcpWithOptions | Set if the NIC is capable of performing LSO on TCP packets with options |
| NetAdapterOffloadLayer4FlagUdp | Set if the NIC is capable of performing USO on UDP packets |

### -field Layer4OffsetLimit

The maximum layer 4 header offset that the NIC supports in bytes. This field is optional.

### -field MaximumOffloadSize

The maximum bytes of user data that the transport can pass to the NIC driver in a single packet.
 
### -field MinimumSegmentCount
 
The minimum number of segments by which a large TCP/UDP packet must be divisible before the transport can offload it to the hardware for segmentation.

### -field EvtAdapterOffloadSetGso

A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_OFFLOAD_SET_GSO*](nc-netadapteroffload-evt_net_adapter_offload_set_gso.md) callback function.

## -remarks

Call [**NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES_INIT**](nf-netadapteroffload-net_adapter_offload_gso_capabilities_init.md) to initialize this structure. The client driver passes an initialized  **NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES** structure as a parameter to [**NetAdapterOffloadSetGsoCapabilities**](nf-netadapteroffload-netadapteroffloadsetgsocapabilities.md).

## -see-also

[Generic Segmentation Offload](/windows-hardware/drivers/netcx/gso-offload)

[**NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES_INIT**](nf-netadapteroffload-net_adapter_offload_gso_capabilities_init.md)

[**NetAdapterOffloadSetGsoCapabilities**](nf-netadapteroffload-netadapteroffloadsetgsocapabilities.md)

[*EVT_NET_ADAPTER_OFFLOAD_SET_GSO*](nc-netadapteroffload-evt_net_adapter_offload_set_gso.md)
