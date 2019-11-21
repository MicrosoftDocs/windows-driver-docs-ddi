---
UID: NS:fragment._NET_FRAGMENT
title: _NET_FRAGMENT (fragment.h)
description: Represents one contiguous buffer in memory.
tech.root: netvista
ms.assetid: 7836111a-f6e9-4177-858d-a05a30a2ec1a
ms.date: 09/26/2019
ms.topic: struct
f1_keywords:
 - "fragment/INSTANCE_PARTIAL_INFORMATION"
ms.keywords: _NET_FRAGMENT, NET_FRAGMENT, 
req.header: fragment.h
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
req.typenames: NET_FRAGMENT, *PNET_FRAGMENT
topictype: 
- apiref
apitype: 
- HeaderDef
apilocation: 
- fragment.h
apiname: 
- NET_FRAGMENT
targetos: Windows
product:
- Windows
---

# _NET_FRAGMENT structure

## -description

Represents one contiguous buffer in memory.

## -struct-fields

### -field ValidLength

Contains the length of packet payload. This value is less than or equal to the value of **Capacity**.

For transmit queues, this value is read-only.

### -field Capacity

Contains the total length of the packet buffer.

For transmit queues, this value is read-only.

### -field Offset

Contains the offset from the start of the **VirtualAddress** and **DmaLogicalAddress** to the start of the valid packet payload. This value is less than or equal to the value of **Capacity**. 

To obtain the virtual address for this fragment, call [**NetExtensionGetFragmentVirtualAddress**](../virtualaddress/nf-virtualaddress-netextensiongetfragmentvirtualaddress.md).

To obtain the DMA logical address for this fragment, call [**NetExtensionGetFragmentLogicalAddress**](../logicaladdress/nf-logicaladdress-netextensiongetfragmentlogicaladdress.md).

For transmit queues, this value is read-only.

### -field Scratch

A bit field value that the client may use for any purpose. When the [**NET_PACKET**](../packet/ns-packet-_net_packet.md) to which this fragment belongs is reused, this value is reset to zero.

### -field OsReserved_Bounced

Reserved. Client drivers must not read or write to this value.

## -remarks

A single [**NET_PACKET**](../packet/ns-packet-_net_packet.md) structure contains references to one or more **NET_FRAGMENT** structures.

While each fragment is a virtually contiguous buffer of memory, a packet that contains more than one fragment is virtually discontiguous.

## -see-also
