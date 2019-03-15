---
UID: NF:netrxqueue.NetRxQueueGetDatapathDescriptor
title: NetRxQueueGetDatapathDescriptor function (netrxqueue.h)
description: The NetRxQueueGetDatapathDescriptor method retrieves the NET_DATAPATH_DESCRIPTOR structure for a receive (Rx) queue.
tech.root: netvista
ms.assetid: 18ae9b71-b6a3-4a6f-ab70-74332b852338
ms.date: 07/13/2018
ms.topic: function
ms.keywords: NetRxQueueGetDatapathDescriptor
req.header: netrxqueue.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
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
topictype: 
- apiref
apitype: 
- DllExport
apilocation: 
- NtosKrnl.exe
apiname: 
- NetRxQueueGetDatapathDescriptor
product:
- Windows
targetos: Windows

---

# NetRxQueueGetDatapathDescriptor function


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NetRxQueueGetDatapathDescriptor** method retrieves the [**NET_DATAPATH_DESCRIPTOR**](../netdatapathdescriptor/ns-netdatapathdescriptor-_net_datapath_descriptor.md) structure for a receive (Rx) queue.

## -parameters

### -param NetRxQueue
A pointer to a **NETPACKETQUEUE** structure. The client driver receives a pointer to this **NETPACKETQUEUE** structure in its *[EVT_NET_ADAPTER_CREATE_RXQUEUE](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)* callback function.

## -returns
Returns a pointer to the queue's [[**NET_DATAPATH_DESCRIPTOR**](../netdatapathdescriptor/ns-netdatapathdescriptor-_net_datapath_descriptor.md) structure.

## -remarks
Use the [[**NET_DATAPATH_DESCRIPTOR**](../netdatapathdescriptor/ns-netdatapathdescriptor-_net_datapath_descriptor.md) structure returned by this method to access a receive queue's packet ring buffer.

## -see-also
