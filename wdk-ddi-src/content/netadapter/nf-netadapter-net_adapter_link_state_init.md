---
UID: NF:netadapter.NET_ADAPTER_LINK_STATE_INIT
title: NET_ADAPTER_LINK_STATE_INIT function (netadapter.h)
description: Initializes a NET_ADAPTER_LINK_STATE structure.
tech.root: netvista
ms.assetid: 6cb7595b-d33f-40fb-a1da-319b31bbeadc
ms.date: 02/06/2018
ms.topic: function
f1_keywords:
 - "netadapter/NET_ADAPTER_LINK_STATE_INIT"
ms.keywords: NET_ADAPTER_LINK_STATE_INIT
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.irql: <= DISPATCH_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
req.typenames: NET_ADAPTER_LINK_STATE_INIT
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netadapter.h
api_name: 
- NET_ADAPTER_LINK_STATE_INIT
targetos: Windows
product:
- Windows
---

# NET_ADAPTER_LINK_STATE_INIT function


## -description



Initializes a [NET_ADAPTER_LINK_STATE](ns-netadapter-_net_adapter_link_state.md) structure.

## -parameters

### -param LinkState
A pointer to a driver-allocated [NET_ADAPTER_LINK_STATE](ns-netadapter-_net_adapter_link_state.md) structure.

### -param LinkSpeed
The link speed of the adapter in bits per second.

### -param MediaConnectState
The media connect state for the network adapter.

### -param MediaDuplexState
The media duplex state for the network adapter.

### -param SupportedPauseFunctions
Support for the IEEE 802.3 pause frames specified by a [**NET_ADAPTER_PAUSE_FUNCTION_TYPE**](../netadapter/ne-netadapter-_net_adapter_pause_function_type.md) value.

### -param AutoNegotiationFlags
The auto-negotiation settings for the network adapter. For more info, see [NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES](../ndis/ns-ndis-_ndis_miniport_adapter_general_attributes.md).

## -returns

This method does not return a value.

## -remarks

Call **NET_ADAPTER_LINK_STATE_INIT** or [NET_ADAPTER_LINK_STATE_INIT_DISCONNECTED](nf-netadapter-net_adapter_link_state_init_disconnected.md) to initialize a [NET_ADAPTER_LINK_STATE](ns-netadapter-_net_adapter_link_state.md) structure.

An initialized **NET_ADAPTER_LINK_STATE** structure is an input parameter value to [NetAdapterSetLinkState](nf-netadapter-netadaptersetlinkstate.md).



## -see-also

[NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES](../ndis/ns-ndis-_ndis_miniport_adapter_general_attributes.md)

[NetAdapterSetLinkState](nf-netadapter-netadaptersetlinkstate.md)

[NET_ADAPTER_LINK_STATE_INIT_DISCONNECTED](nf-netadapter-net_adapter_link_state_init_disconnected.md)

[NET_ADAPTER_LINK_STATE](ns-netadapter-_net_adapter_link_state.md)
