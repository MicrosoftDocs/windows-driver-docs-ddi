---
UID: NF:netadapter.NetAdapterSetDataPathCapabilities
title: NetAdapterSetDataPathCapabilities function (netadapter.h)
description: Sets the data path capabilities of the network adapter.
tech.root: netvista
ms.assetid: 00abe85f-5c61-4fc3-b863-ca31a5989376
ms.date: 02/06/2018
keywords: ["NetAdapterSetDataPathCapabilities function"]
ms.keywords: NetAdapterSetDataPathCapabilities
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.25
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
req.typenames: NetAdapterSetDataPathCapabilities
targetos: Windows
f1_keywords:
 - NetAdapterSetDataPathCapabilities
 - netadapter/NetAdapterSetDataPathCapabilities
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - NetAdapterSetDataPathCapabilities
---

# NetAdapterSetDataPathCapabilities function


## -description

Sets the data path capabilities of the network adapter.

## -parameters

### -param Adapter

The network adapter object that the client created in a prior call to [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

### -param TxCapabilities

A pointer to an allocated and initialized [NET_ADAPTER_TX_CAPABILITIES](ns-netadapter-_net_adapter_tx_capabilities.md) structure.

### -param RxCapabilities

A pointer to an allocated and initialized [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md) structure.

## -remarks

The client driver must call this method when starting a net adapter, before calling [**NetAdapterStart**](nf-netadapter-netadapterstart.md).

This method, along with a few other set capability methods (see below), is the replacement for the [NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES](../ndis/ns-ndis-_ndis_miniport_adapter_general_attributes.md) union that a (non-WDF) client of Ndis.sys sets by calling [NdisMSetMiniportAttributes](../ndis/nf-ndis-ndismsetminiportattributes.md).

## -see-also

[NetAdapterSetLinkLayerCapabilities](nf-netadapter-netadaptersetlinklayercapabilities.md)

[NetAdapterSetPowerCapabilities](nf-netadapter-netadaptersetpowercapabilities.md)

