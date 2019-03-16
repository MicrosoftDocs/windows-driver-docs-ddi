---
UID: NS:netadapter._NET_ADAPTER_LINK_STATE
title: _NET_ADAPTER_LINK_STATE (netadapter.h)
description: Describes the link state of the adapter.
tech.root: netvista
ms.assetid: 0f984325-b393-4b7b-9572-edcef0248b93
ms.date: 02/06/2018
ms.topic: struct
ms.keywords: _NET_ADAPTER_LINK_STATE, NET_ADAPTER_LINK_STATE, *PNET_ADAPTER_LINK_STATE, 
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_ADAPTER_LINK_STATE, *PNET_ADAPTER_LINK_STATE 
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netadapter.h
api_name: 
- NET_ADAPTER_LINK_STATE
product:
- Windows
targetos: Windows
product:
- Windows
---

# _NET_ADAPTER_LINK_STATE structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Describes the link state of the adapter.

## -struct-fields

### -field Size
The size of the **NET_ADAPTER_LINK_STATE** structure, in bytes.
 
### -field TxLinkSpeed
The current transmit link speed of the adapter in bits per second.
 
### -field RxLinkSpeed
The current receive link speed of the adapter in bits per second.
 
### -field MediaConnectState
The media connect state for the network adapter.
 
### -field MediaDuplexState
The media duplex state for the network adapter.
 
### -field SupportedPauseFunctions
Support for the IEEE 802.3 pause frames. For more info, see [NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES](../ndis/ns-ndis-_ndis_miniport_adapter_general_attributes.md).
 
### -field AutoNegotiationFlags
The auto-negotiation settings for the network adapter. For more info, see [NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES](../ndis/ns-ndis-_ndis_miniport_adapter_general_attributes.md).

## -remarks
Call [NET_ADAPTER_LINK_STATE_INIT](nf-netadapter-net_adapter_link_state_init.md) or [NET_ADAPTER_LINK_STATE_INIT_DISCONNECTED](nf-netadapter-net_adapter_link_state_init_disconnected.md) to initialize this structure.

An initialized **NET_ADAPTER_LINK_STATE** structure is an input parameter value to [NetAdapterSetCurrentLinkState](nf-netadapter-netadaptersetcurrentlinkstate.md).



## -see-also

[NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES](../ndis/ns-ndis-_ndis_miniport_adapter_general_attributes.md)

[NET_ADAPTER_LINK_STATE_INIT](nf-netadapter-net_adapter_link_state_init.md)

[NET_ADAPTER_LINK_STATE_INIT_DISCONNECTED](nf-netadapter-net_adapter_link_state_init_disconnected.md)

[NetAdapterSetCurrentLinkState](nf-netadapter-netadaptersetcurrentlinkstate.md)
