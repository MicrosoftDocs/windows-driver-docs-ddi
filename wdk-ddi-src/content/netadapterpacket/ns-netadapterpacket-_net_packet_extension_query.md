---
UID: NS:netadapterpacket._NET_PACKET_EXTENSION_QUERY
title: _NET_PACKET_EXTENSION_QUERY
author: windows-driver-content
description: The NET_PACKET_EXTENSION_QUERY structure represents a query for a packet extension.
ms.assetid: bcfc5079-8a95-4d26-9e8a-bef7d8d08e5c
ms.author: windowsdriverdev
ms.date: 03/01/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NET_PACKET_EXTENSION_QUERY, NET_PACKET_EXTENSION_QUERY, *PNET_PACKET_EXTENSION_QUERY, 
req.header: netadapterpacket.h
req.include-header: netadaptercx.h
req.target-type: 
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: NET_PACKET_EXTENSION_QUERY, *PNET_PACKET_EXTENSION_QUERY
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapterpacket.h
apiname: 
-	_NET_PACKET_EXTENSION_QUERY
product:
-	Windows
targetos: Windows
---

# _NET_PACKET_EXTENSION_QUERY structure

## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NET_PACKET_EXTENSION_QUERY** structure represents a query for a packet extension.

## -struct-fields

### -field Size
The size of this structure, in bytes.
 
### -field Name
The name of the extension to be queried.
 
### -field Version
The version of the extension to be queried.

## -remarks
Call [NET_PACKET_EXTENSION_QUERY_INIT](nf-netadapterpacket-net_packet_extension_query_init.md) to initialize this structure. 

This structure represents a query for a packet extension, whereas the similar [NET_PACKET_EXTENSION_QUERY](ns-netadapterpacket-_net_packet_extension_query.md) structure represents the extension itself.

After initializing this structure with the name and version of the extension, pass it to **NetTx(Rx)QueueGetPacketExtensionOffset** to get that extension's offset for packets in a datapath queue. 

For more information about packet extensions and available packet extension constants, see [Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions). For a code sample, see *[EvtNetAdapterCreateTxQueue](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)* or *[EvtNetAdapterCreateRxQueue](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)*.



## -see-also