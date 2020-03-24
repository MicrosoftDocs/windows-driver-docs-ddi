---
UID: NS:netadapterpacket._NET_EXTENSION_QUERY
title: NET_EXTENSION_QUERY (netadapterpacket.h)
author: windows-driver-content
description: The NET_EXTENSION_QUERY structure represents a query for a packet or fragment extension.
tech.root: netvista
ms.assetid: c5f5ab4a-886a-4eee-bc5d-dc73bbfe5c72
ms.author: windowsdriverdev
ms.date: 11/07/2019
keywords: ["NET_EXTENSION_QUERY structure"]
f1_keywords:
 - "netadapterpacket/NET_EXTENSION_QUERY"
ms.keywords: NET_EXTENSION_QUERY, NET_EXTENSION_QUERY, 
req.header: netadapterpacket.h
req.include-header:
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
targetos: Windows
ms.custom: Vb
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

For more info about extensions, see [Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions). 

For a code example of querying extension offsets, see [Transmit and receive queues](https://docs.microsoft.com/windows-hardware/drivers/netcx/transmit-and-receive-queues).

## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[Transmit and receive queues](https://docs.microsoft.com/windows-hardware/drivers/netcx/transmit-and-receive-queues)

[**NET_EXTENSION_QUERY_INIT**](../netadapterpacket/nf-netadapterpacket-net_extension_query_init.md)

[**NET_EXTENSION_TYPE**](../extension/ne-extension-_net_extension_type.md)
