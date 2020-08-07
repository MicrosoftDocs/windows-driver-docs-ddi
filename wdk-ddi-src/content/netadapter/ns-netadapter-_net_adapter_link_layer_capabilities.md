---
UID: NS:netadapter._NET_ADAPTER_LINK_LAYER_CAPABILITIES
title: _NET_ADAPTER_LINK_LAYER_CAPABILITIES (netadapter.h)
description: Describes the link layer capabilities of the adapter.
tech.root: netvista
ms.assetid: 24888f71-0e12-41c8-a218-9289b1f5b288
ms.date: 09/27/2019
keywords: ["NET_ADAPTER_LINK_LAYER_CAPABILITIES structure"]
f1_keywords:
 - "netadapter/NET_ADAPTER_LINK_LAYER_CAPABILITIES"
 - "NET_ADAPTER_LINK_LAYER_CAPABILITIES"
ms.keywords: _NET_ADAPTER_LINK_LAYER_CAPABILITIES, *PNET_ADAPTER_LINK_LAYER_CAPABILITIES, NET_ADAPTER_LINK_LAYER_CAPABILITIES, 
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.23
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_ADAPTER_LINK_LAYER_CAPABILITIES, *PNET_ADAPTER_LINK_LAYER_CAPABILITIES
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netadapter.h
api_name: 
- NET_ADAPTER_LINK_LAYER_CAPABILITIES
targetos: Windows
---

# _NET_ADAPTER_LINK_LAYER_CAPABILITIES structure

## -description

Describes the link layer capabilities of the adapter.

## -struct-fields

### -field Size

The size of this structure, in bytes.
 
### -field MaxTxLinkSpeed

The maximum transmit link speed of the adapter in bits per second. For more information, see [OID_GEN_MAX_LINK_SPEED](https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-max-link-speed).
 
### -field MaxRxLinkSpeed

 The maximum receive link speed of the adapter in bits per second. For more information, see [OID_GEN_MAX_LINK_SPEED](https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-max-link-speed).

## -remarks

The client driver passes an initialized **NET_ADAPTER_LINK_LAYER_CAPABILITIES** structure as an input parameter value to [NetAdapterSetLinkLayerCapabilities](nf-netadapter-netadaptersetlinklayercapabilities.md).

Call [NET_ADAPTER_LINK_LAYER_CAPABILITIES_INIT](nf-netadapter-net_adapter_link_layer_capabilities_init.md) to initialize this structure.

## -see-also
