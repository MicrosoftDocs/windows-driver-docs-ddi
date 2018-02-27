---
UID: NA:wsk
ms.assetid: 299d7385-fc5c-3b4d-91f8-ca12894ed875
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wsk.h header



This header is used by Networking drivers for Windows Vista and later. For more information, see
- [Networking drivers for Windows Vista and later](../_netvista/index.md)

Wsk.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WskCaptureProviderNPI function](nf-wsk-wskcaptureprovidernpi.md) | The WskCaptureProviderNPI function captures a provider Network Programming Interface (NPI) when it becomes available from the WSK subsystem. |
| [WskDeregister function](nf-wsk-wskderegister.md) | The WskDeregister function unregisters a WSK application's registration instance that was previously created by WskRegister. |
| [WskQueryProviderCharacteristics function](nf-wsk-wskqueryprovidercharacteristics.md) | The WskQueryProviderCharacteristics function queries the range of WSK NPI versions supported by the WSK subsystem. |
| [WskRegister function](nf-wsk-wskregister.md) | The WskRegister function registers a WSK application, given the application's WSK client Network Programming Interface (NPI). |
| [WskReleaseProviderNPI function](nf-wsk-wskreleaseprovidernpi.md) | The WskReleaseProviderNPI function releases a Network Programming Interface (NPI) that was captured with WskCaptureProviderNPI. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PFN_WSK_ABORT_EVENT callback](nc-wsk-pfn_wsk_abort_event.md) | The WskAbortEvent event callback function notifies a WSK application that an incoming connection request on a listening socket that has conditional accept mode enabled has been dropped. |
| [PFN_WSK_ACCEPT callback](nc-wsk-pfn_wsk_accept.md) | The WskAccept function accepts an incoming connection on a listening socket. |
| [PFN_WSK_ACCEPT_EVENT callback](nc-wsk-pfn_wsk_accept_event.md) | The WskAcceptEvent event callback function notifies a WSK application that an incoming connection on a listening socket has been accepted. |
| [PFN_WSK_BIND callback](nc-wsk-pfn_wsk_bind.md) | The WskBind function binds a socket to a local transport address. |
| [PFN_WSK_CLIENT_EVENT callback](nc-wsk-pfn_wsk_client_event.md) | The WskClientEvent event callback function notifies a WSK application about events that are not specific to a particular socket. |
| [PFN_WSK_CLOSE_SOCKET callback](nc-wsk-pfn_wsk_close_socket.md) | The WskCloseSocket function closes a socket and frees any associated resources. |
| [PFN_WSK_CONNECT callback](nc-wsk-pfn_wsk_connect.md) | The WskConnect function connects a connection-oriented or stream socket to a remote transport address. |
| [PFN_WSK_CONNECT_EX callback](nc-wsk-pfn_wsk_connect_ex.md) | The WskConnectEx function connects a connection-oriented or stream socket to a remote transport address.WskConnectEx is similar to WskConnect except that it can also optionally send a buffer of data during or after connection synchronization. |
| [PFN_WSK_CONTROL_CLIENT callback](nc-wsk-pfn_wsk_control_client.md) | The WskControlClient function performs control operations on a WSK client object. |
| [PFN_WSK_CONTROL_SOCKET callback](nc-wsk-pfn_wsk_control_socket.md) | The WskControlSocket function performs control operations on a socket. |
| [PFN_WSK_DISCONNECT callback](nc-wsk-pfn_wsk_disconnect.md) | The WskDisconnect function disconnects a connection-oriented or stream socket from a remote transport address. |
| [PFN_WSK_DISCONNECT_EVENT callback](nc-wsk-pfn_wsk_disconnect_event.md) | The WskDisconnectEvent event callback function notifies a WSK application that a connection on a connection-oriented socket has been disconnected by the remote application. |
| [PFN_WSK_FREE_ADDRESS_INFO callback](nc-wsk-pfn_wsk_free_address_info.md) | The WskFreeAddressInfo function frees address information that the WskGetAddressInfo function has dynamically allocated. |
| [PFN_WSK_GET_ADDRESS_INFO callback](nc-wsk-pfn_wsk_get_address_info.md) | The WskGetAddressInfo function performs protocol-independent translation from a host name to a transport address. |
| [PFN_WSK_GET_LOCAL_ADDRESS callback](nc-wsk-pfn_wsk_get_local_address.md) | The WskGetLocalAddress function retrieves the local transport address of a socket. |
| [PFN_WSK_GET_NAME_INFO callback](nc-wsk-pfn_wsk_get_name_info.md) | The WskGetNameInfo function provides protocol-independent translation from a transport address to a host name. |
| [PFN_WSK_GET_REMOTE_ADDRESS callback](nc-wsk-pfn_wsk_get_remote_address.md) | The WskGetRemoteAddress function retrieves the remote transport address of a connection-oriented or stream socket. |
| [PFN_WSK_INSPECT_COMPLETE callback](nc-wsk-pfn_wsk_inspect_complete.md) | The WskInspectComplete function completes the inspection of a previously pended incoming connection request that was received on a listening socket that has conditional accept mode enabled. |
| [PFN_WSK_INSPECT_EVENT callback](nc-wsk-pfn_wsk_inspect_event.md) | The WskInspectEvent event callback function notifies a WSK application that an incoming connection request on a listening socket that has conditional accept mode enabled has been received. |
| [PFN_WSK_LISTEN callback](nc-wsk-pfn_wsk_listen.md) | The WskListen function enables a stream socket to listen for incoming connections at the socket's bound address. |
| [PFN_WSK_RECEIVE callback](nc-wsk-pfn_wsk_receive.md) | The WskReceive function receives data over a connection-oriented or stream socket from a remote transport address. |
| [PFN_WSK_RECEIVE_EVENT callback](nc-wsk-pfn_wsk_receive_event.md) | The WskReceiveEvent event callback function notifies a WSK application that data has been received on a connection-oriented socket. |
| [PFN_WSK_RECEIVE_FROM callback](nc-wsk-pfn_wsk_receive_from.md) | The WskReceiveFrom function receives a datagram and any associated control information from a remote transport address. |
| [PFN_WSK_RECEIVE_FROM_EVENT callback](nc-wsk-pfn_wsk_receive_from_event.md) | The WskReceiveFromEvent event callback function notifies a WSK application that one or more datagrams have been received on a datagram socket. |
| [PFN_WSK_SEND callback](nc-wsk-pfn_wsk_send.md) | The WskSend function sends data over a connection-oriented or stream socket to a remote transport address. |
| [PFN_WSK_SEND_BACKLOG_EVENT callback](nc-wsk-pfn_wsk_send_backlog_event.md) | The WskSendBacklogEvent event callback function notifies a WSK application when the ideal send backlog size changes for a connection-oriented socket. |
| [PFN_WSK_SEND_TO callback](nc-wsk-pfn_wsk_send_to.md) | The WskSendTo function sends datagram data to a remote transport address. |
| [PFN_WSK_SOCKET callback](nc-wsk-pfn_wsk_socket.md) | The WskSocket function creates a new socket and returns a pointer to the associated socket object. |
| [PFN_WSK_SOCKET_CONNECT callback](nc-wsk-pfn_wsk_socket_connect.md) | The WskSocketConnect function creates a new connection-oriented socket, binds it to a local transport address, connects it to a given remote transport address, and returns a pointer to the associated socket object. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_WSK_BUF structure](ns-wsk-_wsk_buf.md) | The WSK_BUF structure defines a data buffer that is used for sending and receiving data over a socket. |
| [_WSK_CLIENT_CONNECTION_DISPATCH structure](ns-wsk-_wsk_client_connection_dispatch.md) | The WSK_CLIENT_CONNECTION_DISPATCH structure specifies a WSK application's dispatch table of event callback functions for a connection-oriented socket. |
| [_WSK_CLIENT_DATAGRAM_DISPATCH structure](ns-wsk-_wsk_client_datagram_dispatch.md) | The WSK_CLIENT_DATAGRAM_DISPATCH structure specifies a WSK application's dispatch table of event callback functions for a datagram socket. |
| [_WSK_CLIENT_DISPATCH structure](ns-wsk-_wsk_client_dispatch.md) | The WSK_CLIENT_DISPATCH structure specifies a WSK application's dispatch table of event callback functions for events that are not specific to a particular socket. |
| [_WSK_CLIENT_LISTEN_DISPATCH structure](ns-wsk-_wsk_client_listen_dispatch.md) | The WSK_CLIENT_LISTEN_DISPATCH structure specifies a WSK application's dispatch table of event callback functions for a listening socket. |
| [_WSK_CLIENT_NPI structure](ns-wsk-_wsk_client_npi.md) | The WSK_CLIENT_NPI structure identifies a Network Programming Interface (NPI) implemented by a WSK client. |
| [_WSK_CLIENT_STREAM_DISPATCH structure](ns-wsk-_wsk_client_stream_dispatch.md) | The WSK_CLIENT_STREAM_DISPATCH structure specifies a WSK application's dispatch table of event callback functions for a stream socket. |
| [_WSK_DATAGRAM_INDICATION structure](ns-wsk-_wsk_datagram_indication.md) | The WSK_DATAGRAM_INDICATION structure describes a datagram that has been received on a datagram socket. |
| [_WSK_DATA_INDICATION structure](ns-wsk-_wsk_data_indication.md) | The WSK_DATA_INDICATION structure describes data that has been received on a connection-oriented socket. |
| [_WSK_EVENT_CALLBACK_CONTROL structure](ns-wsk-_wsk_event_callback_control.md) | The WSK_EVENT_CALLBACK_CONTROL structure specifies the information for enabling and disabling a socket's event callback functions. |
| [_WSK_EXTENSION_CONTROL_IN structure](ns-wsk-_wsk_extension_control_in.md) | The WSK_EXTENSION_CONTROL_IN structure specifies a WSK application's implementation of an extension interface for a socket. |
| [_WSK_EXTENSION_CONTROL_OUT structure](ns-wsk-_wsk_extension_control_out.md) | The WSK_EXTENSION_CONTROL_OUT structure specifies the WSK subsystem's implementation of an extension interface for a socket. |
| [_WSK_INSPECT_ID structure](ns-wsk-_wsk_inspect_id.md) | The WSK_INSPECT_ID structure specifies an identifier for an incoming connection request on a listening socket. |
| [_WSK_PROVIDER_BASIC_DISPATCH structure](ns-wsk-_wsk_provider_basic_dispatch.md) | The WSK_PROVIDER_BASIC_DISPATCH structure specifies the WSK subsystem's dispatch table of functions for a basic socket. |
| [_WSK_PROVIDER_CHARACTERISTICS structure](ns-wsk-_wsk_provider_characteristics.md) | The WSK_PROVIDER_CHARACTERISTICS structure specifies the characteristics of the WSK subsystem. |
| [_WSK_PROVIDER_CONNECTION_DISPATCH structure](ns-wsk-_wsk_provider_connection_dispatch.md) | The WSK_PROVIDER_CONNECTION_DISPATCH structure specifies the WSK subsystem's table of functions for a connection-oriented socket. |
| [_WSK_PROVIDER_DATAGRAM_DISPATCH structure](ns-wsk-_wsk_provider_datagram_dispatch.md) | The WSK_PROVIDER_DATAGRAM_DISPATCH structure specifies the WSK subsystem's table of functions for a datagram socket. |
| [_WSK_PROVIDER_DISPATCH structure](ns-wsk-_wsk_provider_dispatch.md) | The WSK_PROVIDER_DISPATCH structure specifies the WSK subsystem's dispatch table of functions that are not specific to a particular socket. |
| [_WSK_PROVIDER_LISTEN_DISPATCH structure](ns-wsk-_wsk_provider_listen_dispatch.md) | The WSK_PROVIDER_LISTEN_DISPATCH structure specifies the WSK subsystem's table of functions for a listening socket. |
| [_WSK_PROVIDER_NPI structure](ns-wsk-_wsk_provider_npi.md) | The WSK_PROVIDER_NPI structure identifies a provider Network Programming Interface (NPI) implemented by the WSK subsystem. |
| [_WSK_PROVIDER_STREAM_DISPATCH structure](ns-wsk-_wsk_provider_stream_dispatch.md) | The WSK_PROVIDER_STREAM_DISPATCH structure specifies the WSK subsystem's table of functions for a stream socket. |
| [_WSK_REGISTRATION structure](ns-wsk-_wsk_registration.md) | The WSK_REGISTRATION structure is used by the WSK subsystem to register or unregister a WSK application as a WSK client. |
| [_WSK_SOCKET structure](ns-wsk-_wsk_socket.md) | The WSK_SOCKET structure defines a socket object for a socket. |
| [_WSK_TDI_MAP structure](ns-wsk-_wsk_tdi_map.md) | The WSK_TDI_MAP structure specifies a mapping between a particular address family, socket type, and protocol to the device name of a TDI transport. |
| [_WSK_TDI_MAP_INFO structure](ns-wsk-_wsk_tdi_map_info.md) | The WSK_TDI_MAP_INFO structure specifies a list that contains mappings of a combination of an address family, a socket type, and a protocol to the device name of a TDI transport. |
| [_WSK_TRANSPORT structure](ns-wsk-_wsk_transport.md) | The WSK_TRANSPORT structure specifies an available transport that is supported by the WSK subsystem. |
