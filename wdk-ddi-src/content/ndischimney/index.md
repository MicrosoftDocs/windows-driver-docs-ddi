---
UID: NA:ndischimney
ms.assetid: 900f2233-6276-3f86-a288-4789cc50ae6f
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ndischimney.h header



This header is used by Networking drivers for Windows Vista and later. For more information, see
- [Networking drivers for Windows Vista and later](../_netvista/index.md)

Ndischimney.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [NdisInitiateOffload function](nf-ndischimney-ndisinitiateoffload.md) | A protocol or intermediate driver calls the NdisInitiateOffload function to offload TCP chimney state objects. |
| [NdisInvalidateOffload function](nf-ndischimney-ndisinvalidateoffload.md) | A protocol or intermediate driver calls the NdisInvalidateOffload function to invalidate previously offloaded TCP chimney state objects. |
| [NdisMGetOffloadHandlers function](nf-ndischimney-ndismgetoffloadhandlers.md) | This function obtains the entry points of the NDIS functions for a particular chimney type. |
| [NdisMInitiateOffloadComplete function](nf-ndischimney-ndisminitiateoffloadcomplete.md) | An offload target calls the NdisMInitiateOffloadComplete function to complete an offload operation that was initiated by a previous call to the MiniportInitiateOffload function. |
| [NdisMInvalidateOffloadComplete function](nf-ndischimney-ndisminvalidateoffloadcomplete.md) | An offload target calls the NdisMInvalidateOffloadComplete function to complete an invalidate offload operation that was initiated by a previous call to the MiniportInvalidateOffload function of the offload target. |
| [NdisMOffloadEventIndicate function](nf-ndischimney-ndismoffloadeventindicate.md) | An offload target calls the NdisMOffloadEventIndicate function to indicate various events to the host stack. |
| [NdisMQueryOffloadStateComplete function](nf-ndischimney-ndismqueryoffloadstatecomplete.md) | An offload target calls the NdisMQueryOffloadStateComplete function to complete a query offload operation that was initiated by a previous call to the offload target's MiniportQueryOffload function. |
| [NdisMTerminateOffloadComplete function](nf-ndischimney-ndismterminateoffloadcomplete.md) | An offload target calls the NdisMTerminateOffloadComplete function to complete a terminate offload operation that was initiated by a previous call to the MiniportTerminateOffload function of the offload target. |
| [NdisMUpdateOffloadComplete function](nf-ndischimney-ndismupdateoffloadcomplete.md) | An offload target calls the NdisMUpdateOffloadComplete function to complete an update offload operation that was initiated by a previous call to the MiniportUpdateOffload function of the offload target. |
| [NdisOffloadTcpDisconnect function](nf-ndischimney-ndisoffloadtcpdisconnect.md) | A protocol or intermediate driver calls the NdisOffloadTcpDisconnect function to close the send half of an offloaded TCP connection. |
| [NdisOffloadTcpForward function](nf-ndischimney-ndisoffloadtcpforward.md) | A protocol driver or an intermediate driver calls the NdisOffloadTcpForward function to forward unacknowledged received TCP segments to an underlying driver or offload target. |
| [NdisOffloadTcpReceive function](nf-ndischimney-ndisoffloadtcpreceive.md) | A protocol driver or an intermediate driver calls the NdisOffloadTcpReceive function to post receive requests (receive buffers) on an offloaded TCP connection. |
| [NdisOffloadTcpReceiveReturn function](nf-ndischimney-ndisoffloadtcpreceivereturn.md) | A protocol driver or intermediate driver calls the NdisOffloadTcpReceiveReturn function to return ownership of NET_BUFFER_LIST and associated structures to an underlying offload target. |
| [NdisOffloadTcpSend function](nf-ndischimney-ndisoffloadtcpsend.md) | A protocol driver or intermediate driver calls the NdisOffloadTcpSend function to transmit data on an offloaded TCP connection. |
| [NdisQueryOffloadState function](nf-ndischimney-ndisqueryoffloadstate.md) | A protocol or intermediate driver calls the NdisQueryOffloadState function to query previously offloaded TCP chimney state objects. |
| [NdisTerminateOffload function](nf-ndischimney-ndisterminateoffload.md) | A protocol driver or intermediate driver calls the NdisTerminateOffload function to terminate the offload of one or more state objects |
| [NdisUpdateOffload function](nf-ndischimney-ndisupdateoffload.md) | A protocol or intermediate driver calls the NdisUpdateOffload function to update previously offloaded TCP chimney state objects. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [INDICATE_OFFLOAD_EVENT_HANDLER callback](nc-ndischimney-indicate_offload_event_handler.md) | NDIS calls a protocol driver's or intermediate driver's ProtocolIndicateOffloadEvent function to post an indication that was initiated by an underlying driver's or offload target's call to the NdisMOffloadEventIndicate function. |
| [INITIATE_OFFLOAD_COMPLETE_HANDLER callback](nc-ndischimney-initiate_offload_complete_handler.md) | NDIS calls a protocol driver's or intermediate driver's ProtocolInitiateOffloadComplete function to complete an offload operation that the driver previously initiated by calling the NdisInitiateOffload function. |
| [INVALIDATE_OFFLOAD_COMPLETE_HANDLER callback](nc-ndischimney-invalidate_offload_complete_handler.md) | NDIS calls a protocol driver's or intermediate driver's ProtocolInvalidateOffloadComplete function to complete an invalidate operation that the driver previously initiated by calling the NdisInvalidateOffload function. |
| [NDIS_TCP_OFFLOAD_DISCONNECT_COMPLETE callback](nc-ndischimney-ndis_tcp_offload_disconnect_complete.md) | An offload target calls the NdisTcpOffloadDisconnectComplete function to complete a disconnect request that was initiated by a previous call to the MiniportTcpOffloadDisconnect function of the offload target. |
| [NDIS_TCP_OFFLOAD_EVENT_INDICATE callback](nc-ndischimney-ndis_tcp_offload_event_indicate.md) | An offload target calls the NdisTcpOffloadEventHandler function to indicate an event that pertains to an offloaded TCP connection. |
| [NDIS_TCP_OFFLOAD_FORWARD_COMPLETE callback](nc-ndischimney-ndis_tcp_offload_forward_complete.md) | An offload target calls the NdisTcpOffloadForwardComplete function to complete one or more forward requests that were made to the MiniportTcpOffloadForward function of the offload target. |
| [NDIS_TCP_OFFLOAD_RECEIVE_COMPLETE callback](nc-ndischimney-ndis_tcp_offload_receive_complete.md) | An offload target calls the NdisTcpOffloadReceiveComplete function to return posted receive requests (receive buffers) to the host stack. |
| [NDIS_TCP_OFFLOAD_RECEIVE_INDICATE callback](nc-ndischimney-ndis_tcp_offload_receive_indicate.md) | An offload target calls the NdisTcpOffloadReceiveHandler function to indicate that received network data is available for consumption by a client application. |
| [NDIS_TCP_OFFLOAD_SEND_COMPLETE callback](nc-ndischimney-ndis_tcp_offload_send_complete.md) | An offload target calls the NdisTcpOffloadSendComplete function to complete one or more send requests that were made to the MiniportTcpOffloadSend function of the offload target. |
| [QUERY_OFFLOAD_COMPLETE_HANDLER callback](nc-ndischimney-query_offload_complete_handler.md) | NDIS calls a protocol driver's or intermediate driver's ProtocolQueryOffloadComplete function to complete a query offload operation that the driver previously initiated by calling the NdisQueryOffload function. |
| [TCP_OFFLOAD_DISCONNECT_COMPLETE_HANDLER callback](nc-ndischimney-tcp_offload_disconnect_complete_handler.md) | NDIS calls a protocol driver's or intermediate driver's ProtocolTcpOffloadDisconnectComplete function to complete a disconnect operation that the driver previously initiated by calling the NdisOffloadTcpDisconnect function. |
| [TCP_OFFLOAD_EVENT_HANDLER callback](nc-ndischimney-tcp_offload_event_handler.md) | NDIS calls a protocol driver's or intermediate driver's ProtocolIndicateOffloadEvent function to post an indication that was initiated by an underlying driver's or offload target's call to the NdisTcpOffloadEventHandler function. |
| [TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER callback](nc-ndischimney-tcp_offload_forward_complete_handler.md) | NDIS calls a protocol or intermediate driver's ProtocolTcpOffloadForwardComplete function to complete a forward operation that the driver previously initiated by calling the NdisOffloadTcpForward function. |
| [TCP_OFFLOAD_RECEIVE_INDICATE_HANDLER callback](nc-ndischimney-tcp_offload_receive_indicate_handler.md) | NDIS calls a protocol driver's or intermediate driver's ProtocolTcpOffloadReceiveIndicate function to deliver received data that is being indicated by an underlying driver or offload target. |
| [TCP_OFFLOAD_RECV_COMPLETE_HANDLER callback](nc-ndischimney-tcp_offload_recv_complete_handler.md) | NDIS calls a protocol or intermediate driver's ProtocolTcpOffloadReceiveComplete function to complete a receive operation that the driver previously initiated by calling the NdisOffloadTcpReceive function. |
| [TCP_OFFLOAD_SEND_COMPLETE_HANDLER callback](nc-ndischimney-tcp_offload_send_complete_handler.md) | NDIS calls a protocol or intermediate driver's ProtocolTcpOffloadSendComplete function to complete a send operation that the driver previously initiated by calling the NdisOffloadTcpSend function. |
| [TERMINATE_OFFLOAD_COMPLETE_HANDLER callback](nc-ndischimney-terminate_offload_complete_handler.md) | NDIS calls a protocol or intermediate driver's ProtocolTerminateOffloadComplete function to complete a terminate offload operation that the driver previously initiated by calling the NdisTerminateOffload function. |
| [UPDATE_OFFLOAD_COMPLETE_HANDLER callback](nc-ndischimney-update_offload_complete_handler.md) | NDIS calls a protocol driver's or intermediate driver's ProtocolUpdateOffloadComplete function to complete an update offload operation that the driver previously initiated by calling the NdisUpdateOffload function. |
| [W_INITIATE_OFFLOAD_HANDLER callback](nc-ndischimney-w_initiate_offload_handler.md) | MiniportInitiateOffload offloads TCP chimney state from the host stack. |
| [W_INVALIDATE_OFFLOAD_HANDLER callback](nc-ndischimney-w_invalidate_offload_handler.md) | The MiniportInvalidateOffload function invalidates previously offloaded TCP chimney state objects. |
| [W_QUERY_OFFLOAD_HANDLER callback](nc-ndischimney-w_query_offload_handler.md) | The MiniportQueryOffload function queries previously offloaded TCP chimney state objects. |
| [W_TCP_OFFLOAD_DISCONNECT_HANDLER callback](nc-ndischimney-w_tcp_offload_disconnect_handler.md) | The MiniportTcpOffloadDisconnect function closes the send half of an offloaded TCP connection. |
| [W_TCP_OFFLOAD_FORWARD_HANDLER callback](nc-ndischimney-w_tcp_offload_forward_handler.md) | NDIS calls the MiniportTcpOffloadForward function to forward unacknowledged received TCP segments to an offload target. |
| [W_TCP_OFFLOAD_RECEIVE_HANDLER callback](nc-ndischimney-w_tcp_offload_receive_handler.md) | NDIS calls the MiniportTcpOffloadReceive function to post receive requests (receive buffers) on an offloaded TCP connection. |
| [W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER callback](nc-ndischimney-w_tcp_offload_receive_return_handler.md) | NDIS calls the MiniportTcpOffloadReceiveReturn function to return ownership of NET_BUFFER_LIST and associated structures to an offload target. |
| [W_TCP_OFFLOAD_SEND_HANDLER callback](nc-ndischimney-w_tcp_offload_send_handler.md) | NDIS calls the MiniportTcpOffloadSend function to transmit data on an offloaded TCP connection. |
| [W_TERMINATE_OFFLOAD_HANDLER callback](nc-ndischimney-w_terminate_offload_handler.md) | The MiniportTerminateOffload function terminates the offload of one or more state objects. |
| [W_UPDATE_OFFLOAD_HANDLER callback](nc-ndischimney-w_update_offload_handler.md) | The MiniportUpdateOffload function updates previously offloaded TCP chimney state objects. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_IP_OFFLOAD_STATS structure](ns-ndischimney-_ip_offload_stats.md) | The IP_OFFLOAD_STATS structure contains statistics that an offload target supplies in response to a query of OID_IP4_OFFLOAD_STATS or OID_IP6_OFFLOAD_STATS. |
| [_NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure](ns-ndischimney-_ndis_client_chimney_offload_generic_characteristics.md) | The NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure specifies a protocol driver's generic chimney offload entry points. |
| [_NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure](ns-ndischimney-_ndis_client_chimney_offload_tcp_characteristics.md) | The NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure specifies a protocol or intermediate driver's TCP chimney offload-specific entry points. |
| [_NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure](ns-ndischimney-_ndis_miniport_offload_block_list.md) | The NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure is the basic building block of a TCP chimney offload state tree. An offload state tree can contain one or more NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures. |
| [_NDIS_OFFLOAD_HANDLE structure](ns-ndischimney-_ndis_offload_handle.md) | The NDIS_OFFLOAD_HANDLE structure represents a driver's context for an offloaded state object. |
| [_NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure](ns-ndischimney-_ndis_protocol_offload_block_list.md) | The NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure. |
| [_NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure](ns-ndischimney-_ndis_provider_chimney_offload_generic_characteristics.md) | The NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure specifies the generic chimney offload miniport entry points of an offload target or intermediate driver. |
| [_NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure](ns-ndischimney-_ndis_provider_chimney_offload_tcp_characteristics.md) | The NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure specifies an offload target's TCP chimney offload-specific entry points. |
| [_NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS structure](ns-ndischimney-_ndis_tcp_connection_offload_parameters.md) | The NDIS_TCP_CONNECTION_OFFLOAD_PARAMETERS structure provides TCP chimney offload information in the OID_TCP_CONNECTION_OFFLOAD_PARAMETERS OIDs |
| [_NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure](ns-ndischimney-_ndis_tcp_offload_event_handlers.md) | The NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure contains the entry points for the NDIS functions for the TCP chimney. |
| [_NEIGHBOR_OFFLOAD_STATE_CACHED structure](ns-ndischimney-_neighbor_offload_state_cached.md) | The NEIGHBOR_OFFLOAD_STATE_CACHED structure contains the cached variables of a neighbor state object. |
| [_NEIGHBOR_OFFLOAD_STATE_CONST structure](ns-ndischimney-_neighbor_offload_state_const.md) | The NEIGHBOR_OFFLOAD_STATE_CONST structure contains the constant variables of a neighbor state object. |
| [_NEIGHBOR_OFFLOAD_STATE_DELEGATED structure](ns-ndischimney-_neighbor_offload_state_delegated.md) | The NEIGHBOR_OFFLOAD_STATE_DELGATED structure contains the delegated variable of a neighbor state object. |
| [_OFFLOAD_STATE_HEADER structure](ns-ndischimney-_offload_state_header.md) | The OFFLOAD_STATE_HEADER structure serves as a header in an offload state structure. |
| [_PATH_OFFLOAD_STATE_CACHED structure](ns-ndischimney-_path_offload_state_cached.md) | The PATH_OFFLOAD_STATE_CACHED structure contains the cached variable of a path state object. |
| [_PATH_OFFLOAD_STATE_CONST structure](ns-ndischimney-_path_offload_state_const.md) | The PATH_OFFLOAD_STATE_CONST structure contains the constant variables of a path state object. |
| [_PATH_OFFLOAD_STATE_DELEGATED structure](ns-ndischimney-_path_offload_state_delegated.md) | The PATH_OFFLOAD_STATE_DELEGATED structure contains the delegated variables of a path state object. |
| [_TCP_OFFLOAD_STATE_CACHED structure](ns-ndischimney-_tcp_offload_state_cached.md) | The TCP_OFFLOAD_STATE_CACHED structure contains the cached variables of a TCP connection state object. |
| [_TCP_OFFLOAD_STATE_CONST structure](ns-ndischimney-_tcp_offload_state_const.md) | The TCP_OFFLOAD_STATE_CONST structure contains the constant variables of a TCP connection state object. |
| [_TCP_OFFLOAD_STATE_DELEGATED structure](ns-ndischimney-_tcp_offload_state_delegated.md) | The TCP_OFFLOAD_STATE_DELEGATED structure contains the delegated variables of a TCP connection state object. |
| [_TCP_OFFLOAD_STATS structure](ns-ndischimney-_tcp_offload_stats.md) | The TCP_OFFLOAD_STATS structure contains statistics that an offload target supplies in response to a query of OID_TCP4_OFFLOAD_STATS or OID_TCP6_OFFLOAD_STATS. |
