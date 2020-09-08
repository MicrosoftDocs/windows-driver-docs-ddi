---
UID: NF:netadapter.NET_ADAPTER_LINK_STATE_INIT_DISCONNECTED
title: NET_ADAPTER_LINK_STATE_INIT_DISCONNECTED function (netadapter.h)
description: Initializes a NET_ADAPTER_LINK_STATE structure for an adapter that is disconnected from the network.
tech.root: netvista
ms.assetid: 3c6fe564-8464-4377-ba0f-b83605536322
ms.date: 02/05/2018
keywords: ["NET_ADAPTER_LINK_STATE_INIT_DISCONNECTED function"]
ms.keywords: NET_ADAPTER_LINK_STATE_INIT_DISCONNECTED
req.header: netadapter.h
req.include-header: netadaptercx.h 
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
req.typenames: NET_ADAPTER_LINK_STATE_INIT_DISCONNECTED
targetos: Windows
f1_keywords:
 - NET_ADAPTER_LINK_STATE_INIT_DISCONNECTED
 - netadapter/NET_ADAPTER_LINK_STATE_INIT_DISCONNECTED
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - NET_ADAPTER_LINK_STATE_INIT_DISCONNECTED
---

# NET_ADAPTER_LINK_STATE_INIT_DISCONNECTED function


## -description

Initializes a [NET_ADAPTER_LINK_STATE](ns-netadapter-_net_adapter_link_state.md) structure for an adapter that is disconnected from the network.

## -parameters

### -param LinkState

A pointer to a driver-allocated [NET_ADAPTER_LINK_STATE](ns-netadapter-_net_adapter_link_state.md) structure.

## -remarks

Call [NET_ADAPTER_LINK_STATE_INIT](nf-netadapter-net_adapter_link_state_init.md) or **NET_ADAPTER_LINK_STATE_INIT_DISCONNECTED** to initialize a [NET_ADAPTER_LINK_STATE](ns-netadapter-_net_adapter_link_state.md) structure.

An initialized **NET_ADAPTER_LINK_STATE** structure is an input parameter value to [NetAdapterSetLinkState](nf-netadapter-netadaptersetlinkstate.md).

## -see-also

[NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES](../ndis/ns-ndis-_ndis_miniport_adapter_attributes.md)

[NET_ADAPTER_LINK_STATE_INIT](nf-netadapter-net_adapter_link_state_init.md)

[NET_ADAPTER_LINK_STATE](ns-netadapter-_net_adapter_link_state.md)

[NetAdapterSetLinkState](nf-netadapter-netadaptersetlinkstate.md)

