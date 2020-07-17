---
UID: NF:netadapter.NET_ADAPTER_LINK_LAYER_ADDRESS_INIT
title: NET_ADAPTER_LINK_LAYER_ADDRESS_INIT function (netadapter.h)
description: The NET_ADAPTER_LINK_LAYER_ADDRESS_INIT method initializes a link layer address.
tech.root: netvista
ms.assetid: 13ba4c51-b878-4b22-9260-7bb423b1f77f
ms.date: 02/05/2018
keywords: ["NET_ADAPTER_LINK_LAYER_ADDRESS_INIT function"]
f1_keywords:
 - "netadapter/NET_ADAPTER_LINK_LAYER_ADDRESS_INIT"
 - "NET_ADAPTER_LINK_LAYER_ADDRESS_INIT"
ms.keywords: NET_ADAPTER_LINK_LAYER_ADDRESS_INIT
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type:
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.typenames: NET_ADAPTER_LINK_LAYER_ADDRESS_INIT
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netadapter.h
api_name: 
- NET_ADAPTER_LINK_LAYER_ADDRESS_INIT
targetos: Windows
product:
- Windows
---

# NET_ADAPTER_LINK_LAYER_ADDRESS_INIT function


## -description



The **NET_ADAPTER_LINK_LAYER_ADDRESS_INIT** method initializes a link layer address.

## -parameters

### -param LinkLayerAddress
A pointer to the driver-allocated NET_ADAPTER_LINK_LAYER_ADDRESS to be initialized.

### -param Length
The length of the link layer address, in bytes.

### -param AddressBuffer
A pointer to the buffer containing the link layer address.

## -remarks

**NET_ADAPTER_LINK_LAYER_ADDRESS_INIT** is used to initialize either a permanent or current link layer address, stored in a **NET_ADAPTER_LINK_LAYER_ADDRESS** allocated by the driver. This **NET_ADAPTER_LINK_LAYER_ADDRESS** is then passed as a parameter to either the [NetAdapterSetPermanentLinkLayerAddress](nf-netadapter-netadaptersetpermanentlinklayeraddress.md) method or the [NetAdapterSetCurrentLinkLayerAddress](nf-netadapter-netadaptersetcurrentlinklayeraddress.md) method, depending on the type of address that was initialized and is being set.



## -see-also
