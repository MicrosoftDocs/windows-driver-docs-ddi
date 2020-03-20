---
UID: NF:lso.NetExtensionGetPacketLso
title: NetExtensionGetPacketLso function (lso.h)
author: windows-driver-content
description: The NetExtensionGetPacketLso method retrieves large send offload (LSO) information for a packet.
tech.root: netvista
ms.assetid: 768d42b2-5b31-42a2-bbc0-86c018205a1b
ms.author: windowsdriverdev
ms.date: 09/23/2019
keywords: ["NetExtensionGetPacketLso function"]
f1_keywords:
 - "lso/NetExtensionGetPacketLso"
ms.keywords: NetExtensionGetPacketLso
req.header: lso.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: Any level as long as target memory is resident
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
apitype: 
- DllExport
apilocation: 
- NtosKrnl.exe
api_name: 
- NetExtensionGetPacketLso
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetExtensionGetPacketLso function


## -description

The **NetExtensionGetPacketLso** method retrieves large send offload (LSO) information for a packet.

## -parameters

### -param Extension

A pointer to a [**NET_EXTENSION**](../extension/ns-extension-_net_extension.md) structure that describes the LSO extension information for this transmit queue.

### -param Index

The index in the packet ring for the target [**NET_PACKET**](../packet/ns-packet-_net_packet.md).

## -returns

Returns a pointer to a [**NET_PACKET_LSO**](../lsotypes/ns-lsotypes-_net_packet_lso.md) structure that holds the LSO information for this packet.

## -remarks

NIC client drivers typically query offsets for packet extensions during datapath queue creation, then store them in their queue context space so they don't have to query them too often. For an example of this, see [Transmit and receive queues](https://docs.microsoft.com/windows-hardware/drivers/netcx/transmit-and-receive-queues). Clients can retrieve the LSO offset from the queue context to pass to **NetExtensionGetPacketLso**.

This method is a wrapper method around [**NetExtensionGetData**](../extension/nf-extension-netextensiongetdata.md). 

## -see-also

[Transmit and receive queues](https://docs.microsoft.com/windows-hardware/drivers/netcx/transmit-and-receive-queues)

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[**NetExtensionGetData**](../extension/nf-extension-netextensiongetdata.md)
