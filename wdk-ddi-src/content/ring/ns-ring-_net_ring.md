---
UID: NS:ring._NET_RING
title: _NET_RING (ring.h)
description: Specifies a buffer comprised of one or more NET_PACKET or NET_FRAGMENT structures.
tech.root: netvista
ms.date: 09/25/2019
keywords: ["NET_RING structure"]
ms.keywords: _NET_RING, NET_RING, *PNET_RING,
req.header: ring.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.29
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.alt-api: 
req.alt-loc: 
req.typenames: NET_RING
targetos: Windows
f1_keywords:
 - _NET_RING
 - ring/_NET_RING
 - NET_RING
 - ring/NET_RING
topictype:
 - apiref
apitype:
 - HeaderDef
apilocation:
 - ring.h
apiname:
 - NET_RING
---

# _NET_RING structure


## -description

Specifies a buffer comprised of one or more [**NET_PACKET**](../packet/ns-packet-_net_packet.md) or [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md) structures.

## -struct-fields

### -field OSReserved1

Reserved. Client drivers must not read or write to this value.

### -field ElementStride

A read-only byte offset from the start of one element to the start of the next. Use `((BYTE*)p + ElementStride)` to obtain the address of the next element.

### -field NumberOfElements

A read-only value that indicates the number of packets in the ring buffer, which is always a power of two, and greater than one.

### -field ElementIndexMask

A read-only UINT32 mask that can be used to efficiently clamp an index to **[0, NumberOfElements)**. The client can use this value to calculate an index that wraps around the ring buffer. Use the identity `(x % NumberofElements) == (x & ElementIndexMask)`.

### -field EndIndex

Specifies the read-only index of the last element that is owned by the client driver in the inclusive range [0, **NumberOfElements** - 1].

### -field DUMMYUNIONNAME

A union that contains the **OSReserved0** and **OSReserved2** members.

### -field DUMMYUNIONNAME.OSReserved0

Reserved. Client drivers must not read or write to this value.

### -field DUMMYUNIONNAME.OSReserved2

Reserved. Client drivers must not read or write to this value.

### -field BeginIndex

Specifies the index of the first element owned by the client driver in the inclusive range [0, **NumberOfElements** - 1].

### -field NextIndex

Specifies the index of the next element that needs processing. For optional use by the client driver.

### -field Scratch

A pointer to a buffer that the client driver may use for any purpose.

### -field Buffer

A byte array that contains the elements in the net ring. Typically, a client driver calls [**NetRingGetPacketAtIndex**](../ring/nf-ring-netringgetpacketatindex.md) or [**NetRingGetFragmentAtIndex**](../ring/nf-ring-netringgetfragmentatindex.md) to access the elements of the ring buffer.

## -remarks

The **NET_RING** structure is a generic ring buffer, optimized for efficient access from a single thread. A **NET_RING** contains [**NET_PACKET**](../packet/ns-packet-_net_packet.md) or [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md) elements.

For more info about packet and fragment ring buffers, see [Packet descriptors and extensions](/windows-hardware/drivers/netcx/packet-descriptors-and-extensions#storage-of-packet-descriptors).

For more info about using net rings, see [Introduction to net rings](/windows-hardware/drivers/netcx/introduction-to-net-rings).

## -see-also
