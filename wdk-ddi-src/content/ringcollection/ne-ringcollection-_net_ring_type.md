---
UID: NE:ringcollection._NET_RING_TYPE
title: _NET_RING_TYPE (ringcollection.h)
description: The NET_RING_TYPE enumeration defines types of net rings for a packet queue.
tech.root: netvista
ms.assetid: D14D96AB-E43E-4316-A737-E026C151FA67
ms.date: 02/06/2019
ms.topic: enum
f1_keywords:
 - "ringcollection/RILWRITEPHONEBOOKENTRYPARAMS"
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
topictype: 
- apiref
apitype: 
- HeaderDef
apilocation: 
- ringcollection.h
apiname: 
- _NET_RING_TYPE
product:
- Windows
targetos: Windows
---

# _NET_RING_TYPE enumeration

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NET_RING_TYPE** enumeration defines types of net rings for a packet queue.

## -enum-fields

### -field NET_RING_TYPE_PACKET : 

The [**NET_RING**](../ring/ns-ring-_net_ring.md) is a packet ring.

### -field NET_RING_TYPE_FRAGMENT : 

The [**NET_RING**](../ring/ns-ring-_net_ring.md) is a fragment ring.

## -remarks

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING**](../ring/ns-ring-_net_ring.md)
