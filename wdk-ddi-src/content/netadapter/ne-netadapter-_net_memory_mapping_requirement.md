---
UID: NE:netadapter._NET_MEMORY_MAPPING_REQUIREMENT
title: _NET_MEMORY_MAPPING_REQUIREMENT (netadapter.h)
description: The NET_MEMORY_MAPPING_REQUIREMENT enumeration identifies the memory mapping requirement that a net adapter can specify for its receive and transmit buffers.
tech.root: netvista
ms.assetid: bc46ac6b-7971-408a-ab7b-aa920523bb9d
ms.date: 02/15/2018
f1_keywords:
 - "netadapter/_NET_MEMORY_MAPPING_REQUIREMENT"
ms.keywords: _NET_MEMORY_MAPPING_REQUIREMENT, NET_MEMORY_MAPPING_REQUIREMENT, *PNET_MEMORY_MAPPING_REQUIREMENT, 
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: NET_MEMORY_MAPPING_REQUIREMENT, *PNET_MEMORY_MAPPING_REQUIREMENT
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netadapter.h
api_name: 
- _NET_MEMORY_MAPPING_REQUIREMENT
product:
- Windows
targetos: Windows
---

# _NET_MEMORY_MAPPING_REQUIREMENT enumeration

## -description



The **NET_MEMORY_MAPPING_REQUIREMENT** enumeration identifies the memory mapping requirement that a net adapter can specify for its receive and transmit buffers.

## -enum-fields

### -field NetMemoryMappingRequirementNone : 
The adapter does not require memory mapping.

### -field NetMemoryMappingRequirementDmaMapped : 
The adapter requires DMA mapping for mapping receive or transmit buffers.

## -remarks


## -see-also

[NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md)

[NET_ADAPTER_TX_CAPABILITIES](ns-netadapter-_net_adapter_tx_capabilities.md)
