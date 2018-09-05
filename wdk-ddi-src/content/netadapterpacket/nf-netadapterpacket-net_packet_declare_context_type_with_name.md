---
UID: NF:netadapterpacket.NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME
title: NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME macro
author: windows-driver-content
description: The NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME macro creates an accessor method with a specified name for a client driver's object-specific context space.
ms.assetid: 184fdd5f-0ba3-4c6b-9bf6-2782eee61f5c
ms.author: windowsdriverdev
ms.date: 02/07/2018
ms.topic: macro
ms.keywords: NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME
req.header: netadapterpacket.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.23
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapterpacket.h
apiname: 
-	NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME macro


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME** macro creates an accessor method with a specified name for a client driver's object-specific context space.

## -parameters

### -param _contexttype
The structure type name of a driver-defined structure that describes the contents of an object's context space.

### -param _castingfunction
A C-language routine name. The macro uses this name as the name for the accessor method that it creates for the object's context space. You can put any name you like here; the macro will create a new function with this name.

## -remarks

You can use NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME to define contexts per packet. The per-packet context area is optional.

You may find it helpful to store hardware-specific or bus-specific data in each packet.

NetAdapterCx automatically zeros the context area when the packet is created. The context area is not zeroed out if a packet is reused. If you need to initialize the context areas before the data path starts, initialize them in your *[EvtNetAdapterCreateTxQueue](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)* handler after calling [NetTxQueueCreate](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md); or in the *[EvtNetAdapterCreateRxQueue](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)* handler after calling [NetRxQueueCreate](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md).


### Example

The following examples use a Tx queue.

To declare a context area, use the NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME macro after declaring a structure in a header file:

```C++
typedef struct _MY_TX_PACKET_CONTEXT {
    ULONG MyFlags;
    VOID *MyDescriptor;
} MY_TX_PACKET_CONTEXT;

NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME(MY_TX_PACKET_CONTEXT, GetMyTxPacketContext);
```

Then, when the client creates a queue, associate the packet context with the queue:

```C++
NET_TXQUEUE_CONFIG txQueueConfig;
NET_TXQUEUE_CONFIG_INIT(&txQueueConfig, . . .);

NET_PACKET_CONTEXT_ATTRIBUTES myTxContextAttributes;
NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE(&myTxContextAttributes, MY_TX_PACKET_CONTEXT);

status = NetTxQueueInitAddPacketContextAttributes(txQueueInit, &myTxContextAttributes);

status = NetTxQueueCreate(. . ., &txQueueConfig, . . .);

// Optional: Initialize the context area of each packet to a non-zero value.
NET_RING_BUFFER *ringBuffer = NetTxQueueGetRingBuffer(txQueue);
for (UINT i = 0; i < ringBuffer->NumberOfElements; i++) {
    NET_PACKET *packet = NetRingBufferGetPacketAtIndex(ringBuffer, i);
    MY_TX_PACKET_CONTEXT *context = GetMyTxPacketContext(packet);
    context->MyFlags = 0x1234;
}
```

Then, use the accessor method created by **NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME** to get to your context for a packet.

```C++
NET_PACKET *packet = NetRingBufferGetNextPacket(ringBuffer);
MY_TX_PACKET_CONTEXT *context = GetMyTxPacketContext(packet);

// Do something with the packet context
...
```

## -see-also

[NetPacketGetTypedContext](nf-netadapterpacket-netpacketgettypedcontext.md)

[WDF_DECLARE_CONTEXT_TYPE_WITH_NAME](https://docs.microsoft.com/windows-hardware/drivers/wdf/wdf-declare-context-type-with-name)