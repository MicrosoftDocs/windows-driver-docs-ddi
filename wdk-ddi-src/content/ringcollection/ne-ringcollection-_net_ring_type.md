---
UID: NE:ringcollection._NET_RING_TYPE
title: _NET_RING_TYPE (ringcollection.h)
description: The NET_RING_TYPE enumeration defines types of net rings for a packet queue.
tech.root: netvista
ms.date: 04/01/2022
keywords: ["NET_RING_TYPE enumeration"]
ms.keywords: _NET_RING_TYPE, NET_RING_TYPE,
req.header: ringcollection.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.29
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: NET_RING_TYPE
targetos: Windows
f1_keywords:
 - _NET_RING_TYPE
 - ringcollection/_NET_RING_TYPE
 - NET_RING_TYPE
 - ringcollection/NET_RING_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ringcollection.h
api_name:
 - _NET_RING_TYPE
 - NET_RING_TYPE
---

# _NET_RING_TYPE enumeration


## -description

The **NET_RING_TYPE** enumeration defines types of net rings for a packet queue.

## -enum-fields

### -field NetRingTypePacket:0

The [**NET_RING**](../ring/ns-ring-_net_ring.md) is a packet ring.

### -field NetRingTypeFragment:1 

The [**NET_RING**](../ring/ns-ring-_net_ring.md) is a fragment ring.

### -field NetRingTypeDataBuffer
Reserved for system use.

## -remarks

## -see-also

[Introduction to net rings](/windows-hardware/drivers/netcx/introduction-to-net-rings)

[**NET_RING**](../ring/ns-ring-_net_ring.md)

