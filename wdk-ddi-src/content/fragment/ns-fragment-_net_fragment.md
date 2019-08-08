---
UID: NS:fragment._NET_FRAGMENT
title: _NET_FRAGMENT (fragment.h)
description: Represents one contiguous buffer in memory.
tech.root: netvista
ms.assetid: 7836111a-f6e9-4177-858d-a05a30a2ec1a
ms.date: 01/31/2019
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
product:
- Windows
targetos: Windows
product:
- Windows
---

# _NET_FRAGMENT structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

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

For transmit queues, this value is read-only.

### -field Scratch

A bit field value that the client may use for any purpose. When the [**NET_PACKET**](../packet/ns-packet-_net_packet.md) to which this fragment belongs is reused, this value is reset to zero.

### -field Reserved0

Reserved. Client drivers must not read or write to this value.

### -field OsReserved_Bounced

Reserved. Client drivers must not read or write to this value.

### -field Reserved

Reserved. Client drivers must not read or write to this value.

### -field VirtualAddress

Points to the start of the packet buffer. This address is mapped into the system address space.

For transmit queues, this value is read-only.

### -field DUMMYUNIONNAME

A union that contains the fragment's return context and the **Mapping** union for DMA information.

### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME

A structure that contains the fragment's return context.

### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.RxBufferReturnContext

A pointer to a driver-allocated context space structure. This member is optional and is only used in the receive data path.

For more information about receive path capabilities, see [**NET_ADAPTER_RX_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_rx_capabilities.md).

### -field DUMMYUNIONNAME.Mapping

A union that contains information for DMA.
 
### -field DUMMYUNIONNAME.Mapping.Mdl

For transmit queues, a pointer to an MDL to be used for scatter/gather DMA.

For receive queues, this member is not used.

Do not modify this value.
 
### -field DUMMYUNIONNAME.Mapping.DmaLogicalAddress

For receive queues, contains a mapped DMA address that can be used to program NIC hardware.

For transmit queues, cast this value to an MDL pointer.

Do not modify this value.
 
## -remarks

The **NET_FRAGMENT** structure is similar in concept to a memory descriptor list (MDL).

A single [**NET_PACKET**](../packet/ns-packet-_net_packet.md) structure contains references to one or more **NET_FRAGMENT** structures.

While each fragment is a virtually contiguous buffer of memory, a packet that contains more than one fragment is virtually discontiguous.

The client driver should not unlink, append, or rearrange **NET_FRAGMENT** structures within a [**NET_PACKET**](../packet/ns-packet-_net_packet.md) structure.

## -see-also
