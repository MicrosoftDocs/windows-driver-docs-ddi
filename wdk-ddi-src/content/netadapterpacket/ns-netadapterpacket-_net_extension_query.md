---
UID: NS:netadapterpacket._NET_EXTENSION_QUERY
title: NET_EXTENSION_QUERY (netadapterpacket.h)
description: The NET_EXTENSION_QUERY structure represents a query for a packet or fragment extension.
tech.root: netvista
ms.date: 11/07/2019
keywords: ["NET_EXTENSION_QUERY structure"]
ms.keywords: NET_EXTENSION_QUERY, NET_EXTENSION_QUERY,
req.header: netadapterpacket.h
req.include-header: netadaptercx.h 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NET_EXTENSION_QUERY
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_EXTENSION_QUERY
 - netadapterpacket/_NET_EXTENSION_QUERY
 - NET_EXTENSION_QUERY
 - netadapterpacket/NET_EXTENSION_QUERY
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapterpacket.h
api_name:
 - NET_EXTENSION_QUERY
product:
 - Windows
---

# NET_EXTENSION_QUERY structure


## -description

The **NET_EXTENSION_QUERY** structure represents a query for a packet or fragment extension.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field Name

The name of the extension to be queried.

### -field Version

The version of the extension to be queried.

### -field Type

A [**NET_EXTENSION_TYPE**](../extension/ne-extension-_net_extension_type.md) value that specifies the type of extension being queried.

## -remarks

Call [**NET_EXTENSION_QUERY_INIT**](../netadapterpacket/nf-netadapterpacket-net_extension_query_init.md) to initialize this structure.

For more info about extensions, see [Packet descriptors and extensions](/windows-hardware/drivers/netcx/packet-descriptors-and-extensions). 

For a code example of querying extension offsets, see [Transmit and receive queues](/windows-hardware/drivers/netcx/transmit-and-receive-queues).

## -see-also

[Packet descriptors and extensions](/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[Transmit and receive queues](/windows-hardware/drivers/netcx/transmit-and-receive-queues)

[**NET_EXTENSION_QUERY_INIT**](../netadapterpacket/nf-netadapterpacket-net_extension_query_init.md)

[**NET_EXTENSION_TYPE**](../extension/ne-extension-_net_extension_type.md)
