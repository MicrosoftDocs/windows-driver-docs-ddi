---
UID: NA:netrxqueue
ms.assetid: 88d9b4af-6ff1-3534-b451-a126ba223490
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Netrxqueue.h header



This header is used by Networking drivers for Windows Vista and later. For more information, see
- [Networking drivers for Windows Vista and later](../_netvista/index.md)

Netrxqueue.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [NET_RXQUEUE_CONFIG_INIT function](nf-netrxqueue-net_rxqueue_config_init.md) | Initializes a NET_RXQUEUE_CONFIG structure. |
| [NetRxQueueCreate function](nf-netrxqueue-netrxqueuecreate.md) | Creates a net receive queue object. |
| [NetRxQueueGetDatapathDescriptor function](nf-netrxqueue-netrxqueuegetdatapathdescriptor.md) | The NetRxQueueGetDatapathDescriptor method retrieves the NET_DATAPATH_DESCRIPTOR structure for a receive (Rx) queue. |
| [NetRxQueueGetPacketContextToken function](nf-netrxqueue-netrxqueuegetpacketcontexttoken.md) | The NetRxQueueGetPacketContextToken method retrieves a NET_PACKET_CONTEXT_TOKEN for a NET_PACKET context on a receive queue. |
| [NetRxQueueGetPacketExtensionOffset function](nf-netrxqueue-netrxqueuegetpacketextensionoffset.md) | The NetRxQueueGetPacketExtensionOffset method retrieves the offset, in bytes, to a packet extension for all packets in a receive (Rx) queue. |
| [NetRxQueueInitAddPacketContextAttributes function](nf-netrxqueue-netrxqueueinitaddpacketcontextattributes.md) | The NetRxQueueInitAddPacketContextAttributes method adds an initialized NET_PACKET_CONTEXT_ATTRIBUTES structure to a receive queue's packet context space. |
| [NetRxQueueInitGetQueueId function](nf-netrxqueue-netrxqueueinitgetqueueid.md) | Retrieves the identifier of the receive queue associated with a receive queue. |
| [NetRxQueueNotifyMoreReceivedPacketsAvailable function](nf-netrxqueue-netrxqueuenotifymorereceivedpacketsavailable.md) | The client driver calls NetRxQueueNotifyMoreReceivedPacketsAvailable to resume queue operations after NetAdapterCx calls the client's EVT_RXQUEUE_SET_NOTIFICATION_ENABLED event callback routine. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_RXQUEUE_ADVANCE callback function](nc-netrxqueue-evt_rxqueue_advance.md) | Implemented by the client driver to process receive packets provided by NetAdapterCx. |
| [EVT_RXQUEUE_CANCEL callback function](nc-netrxqueue-evt_rxqueue_cancel.md) | Implemented by the client driver to handle operations that must be performed before a receive queue is deleted. |
| [EVT_RXQUEUE_SET_NOTIFICATION_ENABLED callback function](nc-netrxqueue-evt_rxqueue_set_notification_enabled.md) | Implemented by the client driver to enable receive queue notification for the associated device. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_NET_RXQUEUE_BUFFER_LAYOUT_HINT structure](ns-netrxqueue-_net_rxqueue_buffer_layout_hint.md) | The NET_RXQUEUE_BUFFER_LAYOUT_HINT structure represents receive buffer layout hints returned to a client driver from the upper layer. |
| [_NET_RXQUEUE_CONFIG structure](ns-netrxqueue-_net_rxqueue_config.md) | Describes the configuration options for a NetAdapterCx client driver's receive queue. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [NET_RXQUEUE_GET_PACKET_CONTEXT_TOKEN macro](nf-netrxqueue-net_rxqueue_get_packet_context_token.md) | The NET_RXQUEUE_GET_PACKET_CONTEXT_TOKEN macro retrieves the token identifier for a packet context, for receive queues that use more than one packet context. |
