---
UID: NA:nettxqueue
ms.assetid: 6871a8e7-5bb5-3075-975a-1364c3509ae7
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Nettxqueue.h header



This header is used by NetAdapterCx client drivers. For more information, see
- [Network Adapter WDF Class Extension (Cx)](https://docs.microsoft.com/windows-hardware/drivers/netcx/)

Nettxqueue.h contains these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [NET_TXQUEUE_CONFIG_INIT function](nf-nettxqueue-net_txqueue_config_init.md) | Initializes a NET_TXQUEUE_CONFIG structure. |
| [NetTxQueueCreate function](nf-nettxqueue-nettxqueuecreate.md) | Creates a net transmit queue object. |
| [NetTxQueueGetDatapathDescriptor function](nf-nettxqueue-nettxqueuegetdatapathdescriptor.md) | The NetTxQueueGetDatapathDescriptor method retrieves the NET_DATAPATH_DESCRIPTOR structure for a transmit (Tx) queue. |
| [NetTxQueueGetPacketContextToken function](nf-nettxqueue-nettxqueuegetpacketcontexttoken.md) | The NetTxQueueGetPacketContextToken method retrieves a NET_PACKET_CONTEXT_TOKEN for a NET_PACKET context on a transmit queue. |
| [NetTxQueueGetPacketExtensionOffset function](nf-nettxqueue-nettxqueuegetpacketextensionoffset.md) | The NetTxQueueGetPacketExtensionOffset method retrieves the offset, in bytes, to a packet extension for all packets in a transmit (Tx) queue. |
| [NetTxQueueInitAddPacketContextAttributes function](nf-nettxqueue-nettxqueueinitaddpacketcontextattributes.md) | The NetTxQueueInitAddPacketContextAttributes method adds an initialized NET_PACKET_CONTEXT_ATTRIBUTES structure to a transmit queue's packet context space. |
| [NetTxQueueInitGetQueueId function](nf-nettxqueue-nettxqueueinitgetqueueid.md) | Retrieves the identifier associated with a transmit queue. |
| [NetTxQueueNotifyMoreCompletedPacketsAvailable function](nf-nettxqueue-nettxqueuenotifymorecompletedpacketsavailable.md) | The client driver calls NetTxQueueNotifyMoreCompletedPacketsAvailable to resume queue operations after NetAdapterCx calls the client's EVT_TXQUEUE_SET_NOTIFICATION_ENABLED event callback routine. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_TXQUEUE_ADVANCE callback function](nc-nettxqueue-evt_txqueue_advance.md) | Implemented by the client driver to process transmit packets provided by NetAdapterCx. |
| [EVT_TXQUEUE_CANCEL callback function](nc-nettxqueue-evt_txqueue_cancel.md) | Implemented by the client driver to handle operations that must be performed before a transmit queue is deleted. |
| [EVT_TXQUEUE_SET_NOTIFICATION_ENABLED callback function](nc-nettxqueue-evt_txqueue_set_notification_enabled.md) | Implemented by the client driver to perform client-specific processing when there are new packets received in the specified queue's ring buffer. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_NET_TXQUEUE_CONFIG structure](ns-nettxqueue-_net_txqueue_config.md) | Describes the configuration options for a NetAdapterCx client driver's transmit queue. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [NET_TXQUEUE_GET_PACKET_CONTEXT_TOKEN macro](nf-nettxqueue-net_txqueue_get_packet_context_token.md) | The NET_TXQUEUE_GET_PACKET_CONTEXT_TOKEN macro retrieves a NET_PACKET_CONTEXT_TOKEN for a NET_PACKET context based on the supplied context type name. |
