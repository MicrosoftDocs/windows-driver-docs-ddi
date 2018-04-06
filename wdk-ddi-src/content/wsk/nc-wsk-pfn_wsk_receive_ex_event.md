---
UID: NC:wsk.PFN_WSK_RECEIVE_EX_EVENT
title: PFN_WSK_RECEIVE_EX_EVENT
author: windows-driver-content
description: The WskReceiveExEvent event callback function notifies a WSK application that data has been received on a connection-oriented socket. This callback function is like WskReceiveEvent, but also permits the WSK application to retrieve control information.
ms.assetid: f2e9b1c2-9fb4-448d-9a86-be905ac8bd51
ms.author: windowsdriverdev
ms.date: 04/05/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: wsk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: <= DISPATCH_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	wsk.h
api_name: 
-	PFN_WSK_RECEIVE_EX_EVENT
product: Windows
targetos: Windows
---

# PFN_WSK_RECEIVE_EX_EVENT callback function

## -description

The *WskReceiveExEvent* event callback function notifies a WSK application that data has been received on a connection-oriented socket. This callback function is like [*WskReceiveEvent*](nc-wsk-pfn_wsk_receive_event.md), but also permits the WSK application to retrieve control information.

## -prototype

```
//Declaration

PFN_WSK_RECEIVE_EX_EVENT PfnWskReceiveExEvent; 

// Definition

NTSTATUS PfnWskReceiveExEvent 
(
	PVOID SocketContext
	ULONG Flags
	PWSK_DATA_INDICATION DataIndication
	PCMSGHDR ControlInfo
	ULONG ControlInfoLength
	SIZE_T BytesIndicated
	SIZE_T *BytesAccepted
)
{...}

```

## -parameters

### -param SocketContext 

A pointer to the socket context for the connection-oriented socket that has received the data. The WSK application provided this pointer to the WSK subsystem in one of the following ways:

- It called the [*WskSocket*](nc-wsk-pfn_wsk_socket.md) function to create the socket. 
- It called the [*WskSocketConnect*](nc-wsk-pfn_wsk_socket_connect.md) function to create the socket. 
- It called the [*WskAccept*](nc-wsk-pfn_wsk_accept.md) function to accept the socket as an incoming connection. 
- Its [*WskAcceptEvent*](nc-wsk-pfn_wsk_accept_event.md) event callback function was called to accept the socket as an incoming connection. 

### -param Flags 

A ULONG value that contains a bitwise OR of a combination of the following flags:

| Value | Meaning |
| --- | --- |
| **WSK_FLAG_RELEASE_ASAP** | The data buffers that contain the received data should not be retained by the WSK application if at all possible. If the WSK application retains the buffers, it should release them as soon as possible by calling the [*WskRelease*](https://msdn.microsoft.com/library/windows/hardware/ff571144) function. 
| **WSK_FLAG_ENTIRE_MESSAGE** | The data buffers contain either an entire message or the final portion of a message. The interpretation of what constitutes an entire message is transport protocol-specific. For TCP, this flag indicates that the push bit was set for one or more of the TCP segments that constitute the data in the data buffers. 
| **WSK_FLAG_AT_DISPATCH_LEVEL** | The WSK subsystem called the *WskReceiveExEvent* event callback function at IRQL == DISPATCH_LEVEL. If this flag is not set, the WSK subsystem might have called the *WskReceiveExEvent* event callback function at any IRQL <= DISPATCH_LEVEL. |

### -param DataIndication 

A pointer to a linked list of [**WSK_DATA_INDICATION**](ns-wsk-_wsk_data_indication.md) structures that describe the received data. If this parameter is **NULL**, the socket is no longer functional and the WSK application must call the [*WskCloseSocket*](nc-wsk-pfn_wsk_close_socket.md) function to close the socket as soon as possible.

### -param ControlInfo 

Additional information associated with the received data.

### -param ControlInfoLength 

The length, in bytes, of *ControlInfo*.

### -param BytesIndicated 

The number of bytes of received data described by the linked list of [**WSK_DATA_INDICATION**](ns-wsk-_wsk_data_indication.md) structures.

### -param *BytesAccepted 

A pointer to a SIZE_T-typed variable which receives the number of bytes of received data that is accepted by the WSK application. This variable needs to be set only if the WSK application accepts a portion of the total number of bytes of received data. If the WSK application accepts all of the received data, it does not have to set this variable. If the *WskReceiveExEvent* event callback function returns a status other than STATUS_SUCCESS, the WSK subsystem ignores the value of this variable.

## -returns

A WSK application's *WskReceiveExEvent* event callback function can return one of the following NTSTATUS codes:

| Return code | Description |
| --- | --- |
| **STATUS_SUCCESS** | The WSK application accepted at least some of the received data. If the WSK application accepted all of the received data, the WSK subsystem can call the *WskReceiveExEvent* event callback function again when new data is received on the socket. However, if the WSK application accepted only a portion of the received data, the WSK subsystem will not call the *WskReceiveExEvent* event callback function again until after the WSK application calls the [**WskReceiveEx**](nc-wsk-pfn_wsk_receive_ex.md) function. After the WSK application calls the **WskReceiveEx** function, the WSK subsystem will resume calling the *WskReceiveExEvent* event callback function with any remaining buffered data and when new data is received on the socket. A WSK application can call the **WskReceiveEx** function with a zero-length buffer, which will cause the WSK subsystem to resume calling the *WskReceiveExEvent* event callback function without calling **WskReceiveEx** to receive any data from the socket. |
| **STATUS_PENDING** | The WSK application accepted the data but did not retrieve all of the data contained in the linked list of [**WSK_DATA_INDICATION**](ns-wsk-_wsk_data_indication.md) structures. The WSK application retains the linked list of **WSK_DATA_INDICATION** structures until all of the data has been retrieved. After the WSK application has retrieved all of the data it calls the [*WskRelease*](https://msdn.microsoft.com/library/windows/hardware/ff571144) function to release the linked list of **WSK_DATA_INDICATION** structures back to the WSK subsystem. The WSK subsystem can call the *WskReceiveExEvent* event callback function again when new data is received on the socket.  |
| **STATUS_DATA_NOT_ACCEPTED** | The WSK application did not accept the data. In this situation, the WSK subsystem will have the underlying transport buffer the data if possible or if otherwise required by the protocol. The WSK subsystem will not call the *WskReceiveExEvent* event callback function again until after the WSK application calls the [**WskReceiveEx**](nc-wsk-pfn_wsk_receive_ex.md) function. After the WSK application calls the **WskReceiveEx** function, the WSK subsystem will resume calling the *WskReceiveExEvent* event callback function with any remaining buffered data and when new data is received on the socket. A WSK application can call the **WskReceiveEx** function with a zero-length buffer, which will cause the WSK subsystem to resume calling the *WskReceiveExEvent* event callback function without calling **WskReceiveEx** to receive any data from the socket. |

## -remarks

To enable this event, use the **SIO_WSK_SET_RECEIVE_EX_CALLBACK** IOCTL and supply a *PFN_WSK_RECEIVE_EX_EVENT* callback. To disable this event, use the **SIO_WSK_SET_RECEIVE_EX_CALLBACK** IOCTL and supply **NULL**.

The WSK subsystem calls a WSK application's *WskReceiveExEvent* event callback function when new data is received on a connection-oriented socket only if the event callback function was previously enabled with the SO_WSK_EVENT_CALLBACK socket option. For more information about enabling a socket's event callback functions, see Enabling and Disabling Event Callback Functions.

If a WSK application's *WskReceiveExEvent* event callback function is enabled on a connection-oriented socket and the application also has a pending call to the [**WskReceiveEx**](nc-wsk-pfn_wsk_receive_ex.md) function on the same connection-oriented socket, then, when data arrives, the pending call to the **WskReceiveEx** function will take precedence over the *WskReceiveExEvent* event callback function. The WSK subsystem calls the application's *WskReceiveExEvent* event callback function only if there are no IRPs queued from pending calls to the **WskReceiveEx** function. However, a WSK application should not assume that the WSK subsystem will not call the application's *WskReceiveExEvent* event callback function for a connection-oriented socket that has a pending call to the **WskReceiveEx** function. Race conditions exist where the WSK subsystem could still call the WSK application's *WskReceiveExEvent* event callback function for the socket. The only way for a WSK application to ensure that the WSK subsystem will not call the application's *WskReceiveExEvent* event callback function for a connection-oriented socket is to disable the application's *WskReceiveExEvent* event callback function on the socket.

The WSK subsystem calls a WSK application's *WskReceiveExEvent* event callback function at IRQL <= DISPATCH_LEVEL.

A WSK application's *WskReceiveExEvent* event callback function must not wait for completion of other WSK requests in the context of WSK completion or event callback functions. The callback can initiate other WSK requests (assuming that it doesn't spend too much time at DISPATCH_LEVEL), but it must not wait for their completion even when the callback is called at IRQL == PASSIVE_LEVEL.

## -see-also

[**WSK_CLIENT_CONNECTION_DISPATCH**](ns-wsk-_wsk_client_connection_dispatch.md)

[****WSK_DATA_INDICATION****](ns-wsk-_wsk_data_indication.md)

[*WskAccept*](nc-wsk-pfn_wsk_accept.md)

[*WskAcceptEvent*](nc-wsk-pfn_wsk_accept_event.md)

[*WskCloseSocket*](nc-wsk-pfn_wsk_close_socket.md)

[*WskReceiveEx*](nc-wsk-pfn_wsk_receive_ex.md)

[*WskRelease*](https://msdn.microsoft.com/library/windows/hardware/ff571144)

[*WskSendEx*](nc-wsk-pfn_wsk_send_ex.md)

[*WskSocket*](nc-wsk-pfn_wsk_socket.md)

[*WskSocketConnect*](nc-wsk-pfn_wsk_socket_connect.md)