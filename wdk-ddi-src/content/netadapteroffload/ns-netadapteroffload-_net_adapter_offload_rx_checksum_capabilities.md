---
UID: NS:netadapteroffload._NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES
title: _NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES (netadapteroffload.h)
description: The NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES structure describes a network interface card (NIC)'s capabilities for Rx checksum offload.
tech.root: netvista
ms.assetid: 73c5e8ec-69ef-4c3d-9864-c728f86b3551
ms.date: 01/17/2019
keywords: ["_NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES structure"]
f1_keywords:
 - "netadapteroffload/_NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES"
ms.keywords: _NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES, NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES, *PNET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES, 
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
req.typenames: NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES, *PNET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- netadapteroffload.h
api_name: 
- _NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# _NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES structure

## -description



The **NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES** structure describes a network interface card (NIC)'s capabilities for Rx checksum offload.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field EvtAdapterOffloadSetRxChecksum

A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_OFFLOAD_SET_RX_CHECKSUM*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_rx_checksum.md) callback function.

## -remarks

Call [**NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES_INIT**](../netadapteroffload/nf-netadapteroffload-net_adapter_offload_rx_checksum_capabilities_init.md) to initialize this structure. An initialized **NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES** structure is passed as a parameter to [**NetAdapterOffloadSetRxChecksumCapabilities**](../netadapteroffload/nf-netadapteroffload-netadapteroffloadsetrxchecksumcapabilities.md).

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[**NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES_INIT**](../netadapteroffload/nf-netadapteroffload-net_adapter_offload_rx_checksum_capabilities_init.md)

[**NetAdapterOffloadSetRxChecksumCapabilities**](../netadapteroffload/nf-netadapteroffload-netadapteroffloadsetrxchecksumcapabilities.md)
