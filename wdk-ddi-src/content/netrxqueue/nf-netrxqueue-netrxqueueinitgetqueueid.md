---
UID: NF:netrxqueue.NetRxQueueInitGetQueueId
title: NetRxQueueInitGetQueueId function
author: windows-driver-content
description: Retrieves the identifier of the receive queue associated with a receive queue.
ms.assetid: 588df434-c3f8-4a4a-a9ae-330a825c1d48
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: function
ms.keywords: NetRxQueueInitGetQueueId
req.header: netrxqueue.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
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
-	netrxqueue.h
apiname: 
-	NetRxQueueInitGetQueueId
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetRxQueueInitGetQueueId function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Retrieves the identifier of the receive queue associated with a receive queue.

## -parameters

### -param NetRxQueueInit
A pointer to a NetAdapterCx-allocated **NETRXQUEUE_INIT** structure. For more information, see the Remarks section.

## -returns
Returns a ULONG that identifies a receive queue.

## -remarks
The client driver receives a pointer to a **NETRXQUEUE_INIT** structure in its *[EVT_NET_ADAPTER_CREATE_RXQUEUE](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)* callback function.

Starting with zero, NetAdapterCx assigns an unique identifier value for each queue that it creates. The client driver specifies the number of transmit queues that the network adapter supports in the **MaximumNumberOfQueues** member of the [NET_ADAPTER_RX_CAPABILITIES](../netadapter/ns-netadapter-_net_adapter_rx_capabilities.md) structure, which is initialized and passed to [NetAdapterSetDataPathCapabilities](../netadapter/nf-netadapter-netadaptersetdatapathcapabilities.md) during the *[EvtNetAdapterSetCapabilities](../netadapter/nc-netadapter-evt_net_adapter_set_capabilities.md)* callback function. Identifier values range from zero to the value of `(((MaxNumber of TxQueues) + (MaxNumber of RxQueues)) - 1)`.



## -see-also