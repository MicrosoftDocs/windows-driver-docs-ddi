---
UID: NF:netadapter.NetAdapterSetCurrentLinkLayerAddress
title: NetAdapterSetCurrentLinkLayerAddress function
author: windows-driver-content
description: The NetAdapterSetCurrentLinkLayerAddress method sets the current link layer address for the network adapter.
tech.root: netvista
ms.assetid: bc19abdf-be00-4cbb-bc8b-5a2d59919907
ms.date: 02/06/2018
ms.topic: function
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
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NetAdapterSetCurrentLinkLayerAddress
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NetAdapterSetCurrentLinkLayerAddress function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NetAdapterSetCurrentLinkLayerAddress** method sets the current link layer address for the network adapter.

## -parameters

### -param Adapter
The network adapter object that the driver created in a prior call to [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

### -param LinkLayerAddress
A NET_ADAPTER_LINK_LAYER_ADDRESS object that the driver initialized in a prior call to [NET_ADAPTER_LINK_LAYER_ADDRESS_INIT](nf-netadapter-net_adapter_link_layer_address_init.md).

## -returns
This method does not return a value.

## -remarks


## -see-also
