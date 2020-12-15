---
UID: NF:ring.NetRingGetPacketAtIndex
title: NetRingGetPacketAtIndex function (ring.h)
description: The NetRingGetPacketAtIndex function retrieves a packet from a net ring.
tech.root: netvista
ms.date: 09/25/2019
keywords: ["NetRingGetPacketAtIndex function"]
ms.keywords: NetRingGetPacketAtIndex
req.header: ring.h
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
 - NetRingGetPacketAtIndex
 - ring/NetRingGetPacketAtIndex
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ring.h
api_name:
 - NetRingGetPacketAtIndex
product:
 - Windows
---

# NetRingGetPacketAtIndex function


## -description

The **NetRingGetPacketAtIndex** function retrieves a packet from a net ring.

## -parameters

### -param Ring

A pointer to a [**NET_RING**](../ring/ns-ring-_net_ring.md).

### -param Index

The packet index, within the range **[0, Ring->NumberOfElements)**.

## -returns

Returns a pointer to the [**NET_PACKET**](../packet/ns-packet-_net_packet.md) at the specified index in the packet ring.

## -remarks

This function is a convenient wrapper around [**NetRingGetElementAtIndex**](../ring/nf-ring-netringgetelementatindex.md). Client drivers should call this function when working with a packet ring instead of calling **NetRingGetElementAtIndex** directly.

## -see-also

[**NET_PACKET**](../packet/ns-packet-_net_packet.md)

[**NetRingGetElementAtIndex**](../ring/nf-ring-netringgetelementatindex.md)

