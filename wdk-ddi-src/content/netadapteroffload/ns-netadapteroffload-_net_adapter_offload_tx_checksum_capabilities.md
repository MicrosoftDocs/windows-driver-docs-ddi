---
UID: NS:netadapteroffload._NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES
title: _NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES (netadapteroffload.h)
description: The NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES structure describes a network interface card (NIC)'s capabilities for Tx checksum offload.
tech.root: netvista
ms.assetid:
ms.date: 08/10/2020
keywords: ["_NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES structure"]
f1_keywords:
 - "netadapteroffload/_NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES"
ms.keywords: _NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES, NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES, *PNET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES, 
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
req.typenames: NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES, *PNET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- netadapteroffload.h
api_name: 
- _NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES
product:
- Windows
targetos: Windows
ms.custom: Fe
---

# _NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES structure

## -description

The **NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES** structure describes a network interface card (NIC)'s Tx checksum offload capabilities.

## -struct-fields

### -field Size

The size of this structure in bytes.

### -field Layer3Flags

Flags specifying the layer 3 protocol variations that the NIC can successfully perform Tx checksum on.

The flags should be a combination of:

| Flag | Description |
| --- | --- |
| NetAdapterOffloadLayer3FlagIPv4NoOptions | Set if the NIC is capable of performing IPv4 checksum offload or TCP/UDP checksum offload on IPv4 packets without options |
| NetAdapterOffloadLayer3FlagIPv4WithOptions | Set if the NIC is capable of performing Tx checksum offload on IPv4 packets with options |
| NetAdapterOffloadLayer3FlagIPv6NoExtensions | Set if the NIC is capable of performing Tx checksum offload on IPv6 packets without extensions |
| NetAdapterOffloadLayer3FlagIPv6WithExtensions | Set if the NIC is capable of performing Tx checksum offload on IPv6 packets with extensions |

### -field Layer4Flags

Flags specifying the layer 4 protocol variations that the NIC can successfully perform Tx checksum on.

The flags should be a combination of:

| Flag | Description |
| --- | --- |
| NetAdapterOffloadLayer4FlagTcpNoOptions | Set if the NIC is capable of performing TCP checksum offload |
| NetAdapterOffloadLayer4FlagTcpWithOptions | Set if the NIC is capable of performing Tx checksum offload on TCP packets with options |
| NetAdapterOffloadLayer4FlagUdp | Set if the NIC is capable of performing UDP checksum offload |
 
### -field Layer3HeaderOffsetLimit

The maximum layer 3 header offset that the NIC supports in bytes. This member is optional.

### -field Layer4HeaderOffsetLimit

The maximum layer 4 header offset that the NIC supports in bytes. This member is optional.

### -field EvtAdapterOffloadSetTxChecksum

A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_OFFLOAD_SET_TX_CHECKSUM*](nc-netadapteroffload-evt_net_adapter_offload_set_tx_checksum.md) callback function.

## -remarks

Call [**NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES_INIT**](nf-netadapteroffload-net_adapter_offload_tx_checksum_capabilities_init.md) to initialize this structure. The client driver passes an initialized **NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES** structure as a parameter to [**NetAdapterOffloadSetTxChecksumCapabilities**](nf-netadapteroffload-netadapteroffloadsettxchecksumcapabilities.md).

## -see-also

[NetAdapterCx hardware offloads](/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[Checksum Offload](/windows-hardware/drivers/netcx/checksum-offload)

[*EVT_NET_ADAPTER_OFFLOAD_SET_TX_CHECKSUM*](nc-netadapteroffload-evt_net_adapter_offload_set_tx_checksum.md)

[**NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES_INIT**](nf-netadapteroffload-net_adapter_offload_tx_checksum_capabilities_init.md)

[**NetAdapterOffloadSetTxChecksumCapabilities**](nf-netadapteroffload-netadapteroffloadsettxchecksumcapabilities.md)
