---
UID: NF:netadapter.NetAdapterSetCurrentLinkLayerAddress
title: NetAdapterSetCurrentLinkLayerAddress function (netadapter.h)
description: The NetAdapterSetCurrentLinkLayerAddress function sets the current link layer address for the network adapter.
tech.root: netvista
ms.date: 02/06/2018
keywords: ["NetAdapterSetCurrentLinkLayerAddress function"]
ms.keywords: NetAdapterSetCurrentLinkLayerAddress
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.23
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.alt-api: 
req.alt-loc: 
req.typenames: NetAdapterSetCurrentLinkLayerAddress
targetos: Windows
f1_keywords:
 - NetAdapterSetCurrentLinkLayerAddress
 - netadapter/NetAdapterSetCurrentLinkLayerAddress
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - NetAdapterSetCurrentLinkLayerAddress
---

# NetAdapterSetCurrentLinkLayerAddress function


## -description

The **NetAdapterSetCurrentLinkLayerAddress** function sets the current link layer address for the network adapter.

## -parameters

### -param Adapter

The network adapter object that the driver created in a prior call to [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

### -param LinkLayerAddress

A pointer to a NET_ADAPTER_LINK_LAYER_ADDRESS object that the driver initialized in a prior call to [NET_ADAPTER_LINK_LAYER_ADDRESS_INIT](nf-netadapter-net_adapter_link_layer_address_init.md).

## -remarks

## -see-also

