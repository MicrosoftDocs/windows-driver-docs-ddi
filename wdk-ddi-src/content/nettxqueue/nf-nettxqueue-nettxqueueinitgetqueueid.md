---
UID: NF:nettxqueue.NetTxQueueInitGetQueueId
title: NetTxQueueInitGetQueueId function
author: windows-driver-content
description: Retrieves the identifier associated with a transmit queue.
ms.assetid: 2d76830e-d5eb-4573-bd5a-c4f90a8e0bf1
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: function
ms.keywords: NetTxQueueInitGetQueueId
req.header: nettxqueue.h
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
-	nettxqueue.h
apiname: 
-	NetTxQueueInitGetQueueId
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetTxQueueInitGetQueueId function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Retrieves the identifier associated with a transmit queue.

## -parameters

### -param NetTxQueueInit
A pointer to a NetAdapterCx-allocated **NETTXQUEUE_INIT** structure. For more information, see the Remarks section.

## -returns
Returns a ULONG that identifies a transmit queue.

## -remarks
The client driver receives a pointer to a **NETTXQUEUE_INIT** structure in its *[EVT_NET_ADAPTER_CREATE_TXQUEUE](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)* callback function.

Starting with zero, NetAdapterCx assigns an unique identifier value for each queue that it creates. The client driver specifies the number of transmit queues that the network adapter supports in the **NumTxQueues** member of the [NET_ADAPTER_DATAPATH_CAPABILITIES](../netadapter/ns-netadapter-_net_adapter_datapath_capabilities.md) structure. The client driver passes this structure to [NetAdapterSetDataPathCapabilities](../netadapter/nf-netadapter-netadaptersetdatapathcapabilities.md). Identifier values range from zero to the value of **NumTxQueues** plus **NumRxQueues**, minus one.

The minimum NetAdapterCx version for **NetTxQueueInitGetQueueId** is 1.0.

## -see-also