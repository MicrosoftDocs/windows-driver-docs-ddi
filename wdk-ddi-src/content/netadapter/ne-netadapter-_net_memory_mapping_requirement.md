---
UID: NE:netadapter._NET_MEMORY_MAPPING_REQUIREMENT
title: _NET_MEMORY_MAPPING_REQUIREMENT
author: windows-driver-content
description: The NET_MEMORY_MAPPING_REQUIREMENT enumeration identifies the memory mapping requirement that a net adapter can specify for its receive and transmit buffers.
tech.root: netvista
ms.assetid: bc46ac6b-7971-408a-ab7b-aa920523bb9d
ms.author: windowsdriverdev
ms.date: 02/15/2018
ms.topic: enum
ms.keywords: _NET_MEMORY_MAPPING_REQUIREMENT, NET_MEMORY_MAPPING_REQUIREMENT, *PNET_MEMORY_MAPPING_REQUIREMENT, 
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	_NET_MEMORY_MAPPING_REQUIREMENT
product:
-	Windows
targetos: Windows
---

# _NET_MEMORY_MAPPING_REQUIREMENT enumeration

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

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
