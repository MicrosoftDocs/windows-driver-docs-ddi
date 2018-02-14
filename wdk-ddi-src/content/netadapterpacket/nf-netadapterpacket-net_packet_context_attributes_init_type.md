---
UID: NF:netadapterpacket.NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE
title: NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE macro
author: windows-driver-content
description: The NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE macro initializes a NetAdapterCx client driver's NET_PACKET_CONTEXT_ATTRIBUTES structure for a NET_PACKET and inserts driver-defined context information into the structure.
ms.assetid: b0c8ae6f-e12d-473b-9278-3dc768af9a22
ms.author: windowsdriverdev
ms.date: 02/07/2018
ms.topic: macro
ms.keywords: NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE
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
-	NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE macro


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The **NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE** macro initializes a NetAdapterCx client driver's [NET_PACKET_CONTEXT_ATTRIBUTES](ns-netadapterpacket-_net_packet_context_attributes.md) structure for a [NET_PACKET](../netpacket/ns-netpacket-_net_packet.md) and inserts driver-defined context information into the structure.

## -parameters

### -param _packetcontextattributes
A pointer to a [NET_PACKET_CONTEXT_ATTRIBUTES](ns-netadapterpacket-_net_packet_context_attributes.md) structure.

### -param _contexttype
The structure type name of a driver-defined structure that describes the contents of the packet's context space.

## -remarks

Before calling **NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE**, you must first declare a custom structure for this packet context, then call [NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME](nf-netadapterpacket-net_packet_declare_context_type_with_name.md) globally (not within a function).

The minimum NetAdapterCx version for **NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE** is 1.1.

## Example

In this example, the client driver defines a packet context called **MY_TCB** for its transmit queue, then invokes the [NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME](nf-netadapterpacket-net_packet_declare_context_type_with_name.md) macro to register the structure and specify that the context accessor method will be named **GetMyTcbFromPacket**.

**MY_TCB** is a simple packet context that contains a hardware descriptor for this example client's NIC. TCB stands for Transmit Control Block, indicating that this example context would be used for assistance in transmit operations.

```c++
// in global scope

typedef struct _MY_TCB{
    MY_TX_DESC  *TxDesc;
} MY_TCB;

NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME(MY_TCB, GetMyTcbFromPacket);
```

Then, in its *[EVT_NET_ADAPTER_CREATE_TXQUEUE](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)* callback, the example driver allocates a [NET_PACKET_CONTEXT_ATTRIBUTES](ns-netadapterpacket-_net_packet_context_attributes.md) structure and calls **NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE** to initialize it with the **MY_TCB** type.

```c++
// in EvtNetAdapterCreateTxQueue

...

NET_PACKET_CONTEXT_ATTRIBUTES packetContextAttributes;
NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE(&packetContextAttributes, MY_TCB);

...

```

## -see-also