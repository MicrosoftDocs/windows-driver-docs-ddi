---
UID: NE:extension._NET_EXTENSION_TYPE
title: NET_EXTENSION_TYPE (extension.h)
author: windows-driver-content
description: The NET_EXTENSION_TYPE enumeration specifies the type of extension that a client driver is querying.
tech.root: netvista
ms.assetid: 92541d1b-82e8-4717-9733-3e0e562a9d09
ms.author: windowsdriverdev
ms.date: 09/23/2019
keywords: ["NET_EXTENSION_TYPE enumeration"]
ms.keywords: NET_EXTENSION_TYPE, NET_EXTENSION_TYPE,
req.header: extension.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: NET_EXTENSION_TYPE
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_EXTENSION_TYPE
 - extension/_NET_EXTENSION_TYPE
 - NET_EXTENSION_TYPE
 - extension/NET_EXTENSION_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - extension.h
api_name:
 - NET_EXTENSION_TYPE
product:
 - Windows
---

# NET_EXTENSION_TYPE enumeration


## -description

The **NET_EXTENSION_TYPE** enumeration specifies the type of extension that a client driver is querying.

## -enum-fields

### -field NetExtensionTypePacket 

The extension is a [**NET_PACKET**](../packet/ns-packet-_net_packet.md) extension.

### -field NetExtensionTypeFragment 

The extension is a [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md) extension.

## -remarks

Client drivers pass this enumeration as a value to [**NET_EXTENSION_QUERY_INIT**](../netadapterpacket/nf-netadapterpacket-net_extension_query_init.md) to differentiate between packet extensions and fragment extension queries during packet queue creation.

## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[**NET_PACKET**](../packet/ns-packet-_net_packet.md)

[**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md)

[**NET_EXTENSION_QUERY_INIT**](../netadapterpacket/nf-netadapterpacket-net_extension_query_init.md)

