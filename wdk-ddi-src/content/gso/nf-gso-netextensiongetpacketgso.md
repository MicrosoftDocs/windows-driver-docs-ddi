---
UID: NF:gso.NetExtensionGetPacketGso
tech.root: netvista
title: NetExtensionGetPacketGso
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: The NetExtensionGetPacketGso function retrieves Generic Segmentation Offload (GSO) information for a packet.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: gso.h
req.idl: 
req.include-header: netadaptercx.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - gso.h
api_name:
 - NetExtensionGetPacketGso
f1_keywords:
 - NetExtensionGetPacketGso
 - gso/NetExtensionGetPacketGso
dev_langs:
 - c++
---

## -description

The **NetExtensionGetPacketGso** function retrieves [Generic Segmentation Offload (GSO)](/windows-hardware/drivers/netcx/gso-offload) information for a packet.

## -parameters

### -param Extension

A pointer to a [**NET_EXTENSION**](../extension/ns-extension-_net_extension.md) structure that describes the GSO extension information for this packet queue.

### -param Index

The index in the packet ring for the target [**NET_PACKET**](../packet/ns-packet-_net_packet.md).

## -returns

Returns a pointer to a [**NET_PACKET_GSO**](../gsotypes/ns-gsotypes-net_packet_gso.md) structure that holds the GSO information for this packet.

## -remarks

NIC client drivers typically query offsets for packet extensions during datapath queue creation, then store them in their queue context space so they don't have to query them too often. For an example of this, see [Transmit and receive queues](/windows-hardware/drivers/netcx/transmit-and-receive-queues). Clients can retrieve the GSO offset from the queue context to pass to **NetExtensionGetPacketGso**.

This function is a wrapper function around [**NetExtensionGetData**](../extension/nf-extension-netextensiongetdata.md).

## -see-also 

[Generic Segmentation Offload (GSO)](/windows-hardware/drivers/netcx/gso-offload)

[Packet descriptors and extensions](/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[Transmit and receive queues](/windows-hardware/drivers/netcx/transmit-and-receive-queues)

[**NET_PACKET_GSO**](../gsotypes/ns-gsotypes-net_packet_gso.md)

[**NetExtensionGetData**](../extension/nf-extension-netextensiongetdata.md)

