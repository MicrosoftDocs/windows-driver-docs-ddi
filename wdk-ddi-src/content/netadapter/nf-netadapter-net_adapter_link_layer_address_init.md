---
UID: NF:netadapter.NET_ADAPTER_LINK_LAYER_ADDRESS_INIT
title: NET_ADAPTER_LINK_LAYER_ADDRESS_INIT function (netadapter.h)
description: The NET_ADAPTER_LINK_LAYER_ADDRESS_INIT function initializes a link layer address.
tech.root: netvista
ms.date: 03/30/2022
keywords: ["NET_ADAPTER_LINK_LAYER_ADDRESS_INIT function"]
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
targetos: Windows
f1_keywords:
 - NET_ADAPTER_LINK_LAYER_ADDRESS_INIT
 - netadapter/NET_ADAPTER_LINK_LAYER_ADDRESS_INIT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - NET_ADAPTER_LINK_LAYER_ADDRESS_INIT
---

# NET_ADAPTER_LINK_LAYER_ADDRESS_INIT function


## -description

The **NET_ADAPTER_LINK_LAYER_ADDRESS_INIT** function initializes a link layer address.

## -parameters

### -param LinkLayerAddress [_Out_]

A pointer to the driver-allocated [NET_ADAPTER_LINK_LAYER_ADDRESS](ns-netadapter-net_adapter_link_layer_address.md) structure to be initialized.

### -param Length [_In_range_(1,32)]

The length of the link layer address, in bytes.

### -param AddressBuffer [_In_reads_bytes_(Length)]

A pointer to the buffer containing the link layer address.

## -remarks

**NET_ADAPTER_LINK_LAYER_ADDRESS_INIT** is used to initialize either a permanent or current link layer address, stored in a **NET_ADAPTER_LINK_LAYER_ADDRESS** allocated by the driver. This **NET_ADAPTER_LINK_LAYER_ADDRESS** is then passed as a parameter to either the [NetAdapterSetPermanentLinkLayerAddress](nf-netadapter-netadaptersetpermanentlinklayeraddress.md) function or the [NetAdapterSetCurrentLinkLayerAddress](nf-netadapter-netadaptersetcurrentlinklayeraddress.md) function, depending on the type of address that was initialized and is being set.

## -see-also

[NET_ADAPTER_LINK_LAYER_ADDRESS](ns-netadapter-net_adapter_link_layer_address.md)