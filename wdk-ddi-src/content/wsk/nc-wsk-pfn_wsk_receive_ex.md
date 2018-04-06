---
UID: NC:wsk.PFN_WSK_RECEIVE_EX
title: PFN_WSK_RECEIVE_EX
author: windows-driver-content
description: The WskReceiveEx function receives data over a connection-oriented or stream socket from a remote transport address. This function is like WskReceive, but also permits the WSK application to retrieve control information.
ms.assetid: 461e191a-313d-47c1-b641-fbc5e71319b6
ms.author: windowsdriverdev
ms.date: 04/05/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: wsk.h
req.include-header:
req.target-type: Universal
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
-	PFN_WSK_RECEIVE_EX
product: Windows
targetos: Windows
---

# PFN_WSK_RECEIVE_EX callback function

## -description

The **WskReceiveEx** function receives data over a connection-oriented or stream socket from a remote transport address. This function is like [**WskReceive**](nc-wsk-pfn_wsk_receive.md), but also permits the WSK application to retrieve control information.

## -prototype

```
//Declaration

PFN_WSK_RECEIVE_EX PfnWskReceiveEx; 

// Definition

NTSTATUS PfnWskReceiveEx 
(
	PWSK_SOCKET Socket
	PWSK_BUF Buffer
	ULONG Flags
	PULONG ControlInfoLength
	PCMSGHDR ControlInfo
	PULONG ControlFlags
	PIRP Irp
)
{...}

```

## -parameters

### -param Socket 

A pointer to a [**WSK_SOCKET**](ns-wsk-_wsk_socket.md) structure that specifies the socket object for the socket from which to receive the data.

### -param Buffer 

A pointer to an initialized [**WSK_BUF**](ns-wsk-_wsk_buf.md) structure that describes the data buffer that receives the data from the socket.

### -param Flags 

A ULONG value that contains a bitwise OR of a combination of the following flags:

#### WSK_FLAG_WAITALL

Wait until the data buffer is completely filled. If this flag is specified, the IRP specified in the *Irp* parameter will not be completed until one of the following events occurs:

- The data buffer that is described by the **WSK_BUF** structure that is pointed to by the *Buffer* parameter is completely filled.
- The connection is gracefully disconnected by the remote sender.
- The connection is abortively disconnected by either the WSK application or by the remote sender.
- The specified IRP is canceled.

This flag is supported by the Microsoft TCP/IP transport protocol. This flag might not be supported by other transport protocols.

#### WSK_FLAG_DRAIN

Wait until the socket is disconnected, discarding any data that is received on the socket. If this flag is specified, the specified IRP will not be completed until one of the following events occurs:

- The connection is gracefully disconnected by the remote sender.
- The connection is abortively disconnected by either the WSK application or by the remote sender.
- The specified IRP is canceled.

Any received data is discarded by the WSK subsystem. No received data will be copied into the data buffer. The *Buffer* parameter is still required when this flag is specified, but the length of the buffer that is described by the **WSK_BUF** structure must be zero.

This flag is supported by the Microsoft TCP/IP transport protocol. This flag might not be supported by other transport protocols.

The WSK_FLAG_WAITALL and WSK_FLAG_DRAIN flags are mutually exclusive. A WSK application should not specify both of these flags at the same time.

### -param ControlInfoLength 

A pointer to a ULONG that specifies the length of buffer pointed by *ControlInfo* on input, and the length of actual control data copied into *ControlInfoLength* buffer on output. If *ControlInfoLength* is **NULL** then the *ControlInfo* and *ControlFlags* parameters are ignored. If *ControlInfoLength* is non-**NULL** then *ControlInfoLength* should be pointing to valid memory until the request completes.

### -param ControlInfo 

A pointer to a buffer into which WSK copies the control data received with the datagram. This parameter is ignored if the *ControlInfoLength* parameter is **NULL**. Otherwise, *ControlInfo* should be pointing to valid memory until the request completes.

### -param ControlFlags 

Reserved. WSK applications must set this parameter to **NULL**.

### -param Irp 

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the receive operation asynchronously. For more information about using IRPs with WSK functions, see [Using IRPs with Winsock Kernel Functions](https://docs.microsoft.com/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions).

## -returns

**WskReceiveEx** returns one of the following NTSTATUS codes:

| Return code | Description |
| --- | --- |
| **STATUS_SUCCESS** | Data was successfully received from the socket. The IRP will be completed with success status. The **IoStatus.Information** field of the IRP contains the number of bytes that were received. |
| **STATUS_PENDING** | The WSK subsystem could not receive the data from the socket immediately. The WSK subsystem will complete the IRP after it has received the data from the socket. The status of the receive operation will be returned in the **IoStatus.Status** field of the IRP. If the operation succeeds, the **IoStatus.Information** field of the IRP will contain the number of bytes that were received. |
| **STATUS_FILE_FORCED_CLOSED** | The socket is no longer functional. The IRP will be completed with failure status. The WSK application must call the [*WskCloseSocket*](nc-wsk-pfn_wsk_close_socket.md) function to close the socket as soon as possible. |
| **STATUS_NOT_SUPPORTED** | A specified flag is not supported by the underlying network transport. |
| **Other status codes** | An error occurred. The IRP will be completed with failure status. |

## -remarks

A WSK application can call the **WskReceiveEx** function only on a connection-oriented or stream socket that has been previously connected to a remote transport address. A connection-oriented socket is connected to a remote transport address by one of the following methods:

- The WSK application connects the socket by calling the [*WskConnect*](nc-wsk-pfn_wsk_connect.md) function.
- The WSK application creates, binds, and connects the socket by calling the [*WskSocketConnect*](nc-wsk-pfn_wsk_socket_connect.md) function.
- The WSK subsystem connects the socket when the WSK application accepts an incoming connection request on a listening socket.

If a WSK application's [*WskReceiveExEvent*](nc-wsk-pfn_wsk_receive_ex_event.md) event callback function is enabled on a connection-oriented socket and the application also has a pending call to the **WskReceiveEx** function on the same connection-oriented socket, then, when data arrives, the pending call to the **WskReceiveEx** function will take precedence over the *WskReceiveExEvent* event callback function. The WSK subsystem calls the application's *WskReceiveExEvent* event callback function only if there are no IRPs queued from pending calls to the **WskReceiveEx** function. However, a WSK application should not assume that the WSK subsystem will not call the application's *WskReceiveExEvent* event callback function for a connection-oriented socket that has a pending call to the **WskReceiveEx** function. Race conditions exist where the WSK subsystem could still call the WSK application's *WskReceiveExEvent* event callback function for the socket. The only way for a WSK application to ensure that the WSK subsystem will not call the application's *WskReceiveExEvent* event callback function for a connection-oriented socket is to disable the application's *WskReceiveExEvent* event callback function on the socket.

A WSK application can call the **WskReceiveEx** function with a zero length specified in the Length member of the [**WSK_BUF**](ns-wsk-_wsk_buf.md) structure that is pointed to by the *Buffer* parameter. Specifying a zero length in this member is useful in the following situations:

- When re-enabling the *WskReceiveExEvent* event callback function for a socket after the *WskReceiveExEvent* event callback function previously returned STATUS_DATA_NOT_ACCEPTED.
- When specifying the WSK_FLAG_DRAIN flag to discard any additional data that is received on the socket.

If the **WskReceiveEx** function returns STATUS_PENDING, the MDL chain that is described in the **WSK_BUF** structure that is pointed to by the *Buffer* parameter must remain locked in memory until the IRP is completed.

## -see-also

[**WSK_BUF**](ns-wsk-_wsk_buf.md)

[**WSK_PROVIDER_CONNECTION_DISPATCH**](ns-wsk-_wsk_provider_connection_dispatch.md)

[**WSK_PROVIDER_STREAM_DISPATCH**](ns-wsk-_wsk_provider_stream_dispatch.md)

[**WSK_SOCKET**](ns-wsk-_wsk_socket.md)

[*WskCloseSocket*](nc-wsk-pfn_wsk_close_socket.md)

[*WskReceiveExEvent*](nc-wsk-pfn_wsk_receive_ex_event.md)

[*WskSendEx*](nc-wsk-pfn_wsk_send_ex.md)