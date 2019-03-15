---
UID: NF:netadapter.NetAdapterSetPowerCapabilities
title: NetAdapterSetPowerCapabilities function (netadapter.h)
description: Sets the power capabilities of the network adapter.
tech.root: netvista
ms.assetid: a9a9bfd8-9c90-4b6f-8790-ad61f5af4073
ms.date: 02/06/2018
ms.topic: function
ms.keywords: NetAdapterSetPowerCapabilities
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
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
req.typenames: NetAdapterSetPowerCapabilities
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netadapter.h
api_name: 
- NetAdapterSetPowerCapabilities
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetAdapterSetPowerCapabilities function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Sets the power capabilities of the network adapter.

## -parameters

### -param Adapter
The network adapter object that the client created in a prior call to [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

### -param PowerCapabilities
A pointer to an allocated and initialized [NET_ADAPTER_POWER_CAPABILITIES](ns-netadapter-_net_adapter_power_capabilities.md) structure.

## -returns
This method does not return a value.

## -remarks

The client driver sets capabilities by calling the following methods when starting a net adapter, before calling [**NetAdapterStart**](nf-netadapter-netadapterstart.md).

- [**NetAdapterSetDataPathCapabilities**](nf-netadapter-netadaptersetdatapathcapabilities.md)
- [**NetAdapterSetLinkLayerCapabilities**](nf-netadapter-netadaptersetlinklayercapabilities.md)
- **NetAdapterSetPowerCapabilities**
- [**NetAdapterSetReceiveScalingCapabilities**](../netreceivescaling/nf-netreceivescaling-netadaptersetreceivescalingcapabilities.md)
- [**NetAdapterOffloadSetChecksumCapabilities**](nf-netadapter-netadapteroffloadsetchecksumcapabilities.md)
- [**NetAdapterOffloadSetLsoCapabilities**](nf-netadapter-netadapteroffloadsetlsocapabilities.md)

Alternatively, the client can call **NetAdapterSetPowerCapabilities** at a later time, but it must not change the *[EVT_NET_ADAPTER_PREVIEW_WAKE_PATTERN](nc-netadapter-evt_net_adapter_preview_wake_pattern.md)* and *[EVT_NET_ADAPTER_PREVIEW_PROTOCOL_OFFLOAD](nc-netadapter-evt_net_adapter_preview_protocol_offload.md)* event callback functions.

## -see-also

[NdisMIndicateStatusEx](../ndis/nf-ndis-ndismindicatestatusex.md)

[NdisMSetMiniportAttributes](../ndis/nf-ndis-ndismsetminiportattributes.md)

[NetAdapterSetDataPathCapabilities](nf-netadapter-netadaptersetdatapathcapabilities.md)

[NetAdapterSetLinkLayerCapabilities](nf-netadapter-netadaptersetlinklayercapabilities.md)
