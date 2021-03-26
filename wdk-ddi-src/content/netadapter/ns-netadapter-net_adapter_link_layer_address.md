---
UID: NS:netadapter._NET_ADAPTER_LINK_LAYER_ADDRESS
tech.root: netvista
title: NET_ADAPTER_LINK_LAYER_ADDRESS
ms.date: 04/15/2021
ms.topic: language-reference
targetos: Windows
description: A NET_ADAPTER_LINK_LAYER_ADDRESS structure describes a link layer address.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: netadapter.h
req.include-header: netadaptercx.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 21H1
req.target-min-winversvr: 
req.target-type: 
req.typenames: NET_ADAPTER_LINK_LAYER_ADDRESS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - _NET_ADAPTER_LINK_LAYER_ADDRESS
 - NET_ADAPTER_LINK_LAYER_ADDRESS
f1_keywords:
 - _NET_ADAPTER_LINK_LAYER_ADDRESS
 - netadapter/_NET_ADAPTER_LINK_LAYER_ADDRESS
 - NET_ADAPTER_LINK_LAYER_ADDRESS
 - netadapter/NET_ADAPTER_LINK_LAYER_ADDRESS
dev_langs:
 - c++
---

## -description

A **NET_ADAPTER_LINK_LAYER_ADDRESS** structure describes a link layer address.

## -struct-fields

### -field Length

The length of the link layer address, in bytes.

### -field Address

A buffer containing the link layer address.

## -remarks

## -see-also

[**NET_ADAPTER_LINK_LAYER_ADDRESS_INIT**](nf-netadapter-net_adapter_link_layer_address_init.md)

[**NetAdapterSetPermanentLinkLayerAddress**](nf-netadapter-netadaptersetpermanentlinklayeraddress.md)

[**NET_ADAPTER_LINK_LAYER_CAPABILITIES**](ns-netadapter-_net_adapter_link_layer_capabilities.md)

[**NetAdapterSetCurrentLinkLayerAddress**](nf-netadapter-netadaptersetcurrentlinklayeraddress.md)