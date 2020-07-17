---
UID: NF:netadapter.NetAdapterSetLinkState
title: NetAdapterSetLinkState function (netadapter.h)
description: Sets the current link state of the of the network adapter.
tech.root: netvista
ms.assetid: 5c06c275-4eb8-46ba-9b90-50ca192c9a47
ms.date: 01/18/2019
keywords: ["NetAdapterSetLinkState function"]
f1_keywords:
 - "netadapter/NetAdapterSetLinkLayerMtuSize"
 - "NetAdapterSetLinkLayerMtuSize"
ms.keywords: NetAdapterSetLinkState
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.29
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
req.typenames: NetAdapterSetLinkState
topictype: 
- apiref
apitype: 
- HeaderDef
apilocation: 
- netadapter.h
apiname: 
- NetAdapterSetLinkState
targetos: Windows
product:
- Windows
---

# NetAdapterSetLinkState function


## -description



Sets the link state of the of the network adapter.

## -parameters

### -param Adapter

The network adapter object that the client created in a prior call to [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

### -param State

A pointer to an allocated and initialized [**NET_ADAPTER_LINK_STATE**](ns-netadapter-_net_adapter_link_state.md) structure that describes the link state of the adapter.

## -remarks

The client driver calls **NetAdapterSetLinkState** when starting a net adapter, before it calls [**NetAdapterStart**](nf-netadapter-netadapterstart.md). It can also call this method later when it needs to change the current link state.

## -see-also

[**NET_ADAPTER_LINK_STATE_INIT**](nf-netadapter-net_adapter_link_state_init.md)

[**NET_ADAPTER_LINK_STATE_INIT_DISCONNECTED**](nf-netadapter-net_adapter_link_state_init_disconnected.md)
