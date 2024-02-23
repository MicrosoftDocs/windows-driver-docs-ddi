---
UID: NS:logicaladdresstypes._NET_FRAGMENT_LOGICAL_ADDRESS
title: NET_FRAGMENT_LOGICAL_ADDRESS (logicaladdresstypes.h)
description: The NET_FRAGMENT_LOGICAL_ADDRESS structure contains DMA logical address information for a NET_FRAGMENT.
tech.root: netvista
ms.date: 01/24/2024
keywords: ["NET_FRAGMENT_LOGICAL_ADDRESS structure"]
ms.keywords: NET_FRAGMENT_LOGICAL_ADDRESS, NET_FRAGMENT_LOGICAL_ADDRESS,
req.header: logicaladdresstypes.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NET_FRAGMENT_LOGICAL_ADDRESS
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_FRAGMENT_LOGICAL_ADDRESS
 - logicaladdresstypes/_NET_FRAGMENT_LOGICAL_ADDRESS
 - NET_FRAGMENT_LOGICAL_ADDRESS
 - logicaladdresstypes/NET_FRAGMENT_LOGICAL_ADDRESS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - logicaladdresstypes.h
api_name:
 - _NET_FRAGMENT_LOGICAL_ADDRESS
 - NET_FRAGMENT_LOGICAL_ADDRESS
product:
 - Windows
---

# NET_FRAGMENT_LOGICAL_ADDRESS structure


## -description

The **NET_FRAGMENT_LOGICAL_ADDRESS** structure contains DMA logical address information for a [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md).

## -struct-fields

### -field LogicalAddress

On DMA capable adapters, contains a mapped DMA address that can be used to program NIC hardware.

Do not modify this value.

## -remarks

NetAdapterCx automatically registers the **NET_FRAGMENT_LOGICAL_ADDRESS** extension when the driver advertises DMA capabilities for the receive or transmit path.

To advertise DMA for the receive path, the driver must set the **DmaCapabilities** member in [**NET_ADAPTER_RX_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_rx_capabilities.md) and call [NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED_DMA](../netadapter/nf-netadapter-net_adapter_rx_capabilities_init_system_managed_dma.md) to initialize the structure. 

To advertise DMA for the transmit path, the driver must set the **DmaCapabilities** member in [**NET_ADAPTER_TX_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_tx_capabilities.md) and call [NET_ADAPTER_TX_CAPABILITIES_INIT_FOR_DMA](../netadapter/nf-netadapter-net_adapter_tx_capabilities_init_for_dma.md) to initialize the structure.

To obtain this structure, call [**NetExtensionGetFragmentLogicalAddress**](../logicaladdress/nf-logicaladdress-netextensiongetfragmentlogicaladdress.md).

## -see-also

[Packet descriptors and extensions](/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md)

[**NetExtensionGetFragmentLogicalAddress**](../logicaladdress/nf-logicaladdress-netextensiongetfragmentlogicaladdress.md)

[**NET_ADAPTER_TX_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_tx_capabilities.md)

[**NET_ADAPTER_RX_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_rx_capabilities.md)

