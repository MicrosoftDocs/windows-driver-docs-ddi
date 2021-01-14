---
UID: NS:netadapteroffload._NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES
title: _NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES (netadapteroffload.h)
description: The NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES structure describes a network interface card (NIC)'s capabilities for Rx checksum offload.
tech.root: netvista
ms.date: 10/06/2020
keywords: ["_NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES structure"]
ms.keywords: _NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES, NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES, *PNET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES,
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
req.typenames: NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES, *PNET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES
targetos: Windows
ms.custom: Fe
f1_keywords:
 - _NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES
 - netadapteroffload/_NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES
 - NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES
 - netadapteroffload/NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES
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
---

# _NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES structure


## -description

> [!WARNING]
> Some information in this topic relates to pre-released product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 2004.
>
> Currently, NetAdapterCx client drivers cannot be certified.

The **NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES** structure describes a network interface card (NIC)'s Rx checksum offload capabilities.

## -struct-fields

### -field Size

The size of this structure in bytes.

### -field EvtAdapterOffloadSetRxChecksum

A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_OFFLOAD_SET_RX_CHECKSUM*](nc-netadapteroffload-evt_net_adapter_offload_set_rx_checksum.md) callback function.

## -remarks

Call [**NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES_INIT**](nf-netadapteroffload-net_adapter_offload_rx_checksum_capabilities_init.md) to initialize this structure. The client driver passes an initialized **NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES** structure as a parameter to [**NetAdapterOffloadSetRxChecksumCapabilities**](nf-netadapteroffload-netadapteroffloadsetrxchecksumcapabilities.md).

## -see-also

[Checksum Offload](/windows-hardware/drivers/netcx/checksum-offload)

[*EVT_NET_ADAPTER_OFFLOAD_SET_RX_CHECKSUM*](nc-netadapteroffload-evt_net_adapter_offload_set_rx_checksum.md)

[**NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES_INIT**](nf-netadapteroffload-net_adapter_offload_rx_checksum_capabilities_init.md)

[**NetAdapterOffloadSetRxChecksumCapabilities**](nf-netadapteroffload-netadapteroffloadsetrxchecksumcapabilities.md)

