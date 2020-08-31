---
UID: NF:rsc.NetExtensionGetPacketRsc
title: NetExtensionGetPacketRsc function (rsc.h)
author: windows-driver-content
description: The NetExtensionGetPacketRsc function retrieves receive segment coalescence (RSC) information for a packet.
tech.root: netvista
ms.assetid: 1798e870-cfaf-44fc-920f-4167de3842ef
ms.author: windowsdriverdev
ms.date: 09/24/2019
keywords: ["NetExtensionGetPacketRsc function"]
ms.keywords: NetExtensionGetPacketRsc
req.header: rsc.h
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
targetos: Windows
ms.custom: Vb
f1_keywords:
 - NetExtensionGetPacketRsc
 - rsc/NetExtensionGetPacketRsc
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - rsc.h
api_name:
 - NetExtensionGetPacketRsc
product:
 - Windows
---

# NetExtensionGetPacketRsc function


## -description

The **NetExtensionGetPacketRsc** function retrieves receive segment coalescence (RSC) information for a packet.

## -parameters

### -param Extension

A pointer to a [**NET_EXTENSION**](../extension/ns-extension-_net_extension.md) structure that describes the RSC extension information for this receive queue.

### -param Index

The index in the packet ring for the target [**NET_PACKET**](../packet/ns-packet-_net_packet.md).

## -returns

Returns a pointer to a [**NET_PACKET_RSC**](../rsctypes/ns-rsctypes-_net_packet_rsc.md) structure that holds the RSC information for this packet.

## -remarks

NIC client drivers typically query offsets for packet extensions during datapath queue creation, then store them in their queue context space so they don't have to query them too often. For an example of this, see [Transmit and receive queues](https://docs.microsoft.com/windows-hardware/drivers/netcx/transmit-and-receive-queues). Clients can retrieve the RSC offset from the queue context to pass to **NetExtensionGetPacketRsc**.

This function is a wrapper function around [**NetExtensionGetData**](../extension/nf-extension-netextensiongetdata.md).

## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[**NetExtensionGetData**](../extension/nf-extension-netextensiongetdata.md)

