---
UID: NC:wsk.PFN_WSK_SEND_EX
title: PFN_WSK_SEND_EX
author: windows-driver-content
description: The WskSendEx function sends data over a connection-oriented or stream socket to a remote transport address. This function is like WskSend, but also permits the WSK application to supply control information.
ms.assetid: 3c3f9c67-12fb-43cf-a084-9b1952db94db
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
-	PFN_WSK_SEND_EX
product: Windows
targetos: Windows
---

# PFN_WSK_SEND_EX callback function

## -description

The **WskSendEx** function sends data over a connection-oriented or stream socket to a remote transport address. This function is like [**WskSend**](nc-wsk-pfn_wsk_send.md), but also permits the WSK application to supply control information.

## -prototype

```
//Declaration

PFN_WSK_SEND_EX PfnWskSendEx; 

// Definition

NTSTATUS PfnWskSendEx 
(
	PWSK_SOCKET Socket
	PWSK_BUF Buffer
	ULONG Flags
	ULONG ControlInfoLength
	PCMSGHDR ControlInfo
	PIRP Irp
)
{...}

```

## -parameters

### -param Socket 

A pointer to a [**WSK_SOCKET**](ns-wsk-_wsk_socket.md) structure that specifies the socket object for the socket over which to send the data.

### -param Buffer 

A pointer to an initialized [**WSK_BUF**](ns-wsk-_wsk_buf.md) structure that describes the data buffer that contains the data that is being sent over the socket.

### -param Flags 

A ULONG value that contains a bitwise OR of a combination of the following flags:

#### WSK_FLAG_NODELAY

Directs the underlying transport to immediately send the data, and any previously queued data, to the remote application without delay.

This flag is supported by the Microsoft TCP/IP transport protocol. This flag might not be supported by other transport protocols.

### -param ControlInfoLength 

The length, in bytes, of *ControlInfo*.

### -param ControlInfo 

Additional information to pass to the remote party. This information might not be supported by all transports.

### -param Irp 

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the send operation asynchronously. For more information about using IRPs with WSK functions, see [Using IRPs with Winsock Kernel Functions](https://docs.microsoft.com/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions).

## -returns

**WskSendEx** returns one of the following NTSTATUS codes:

| Return code | Description |
| --- | --- |
| **STATUS_SUCCESS** | Data was successfully sent over the socket. The IRP will be completed with success status. The **IoStatus.Information** field of the IRP contains the number of bytes that were sent.  |
| **STATUS_PENDING** | The WSK subsystem could not send the data over the socket immediately. The WSK subsystem will complete the IRP after it has sent the data over the socket. The status of the send operation will be returned in the **IoStatus.Status** field of the IRP. If the operation succeeds, the **IoStatus.Information** field of the IRP will contain the number of bytes that were sent.  |
| **STATUS_FILE_FORCED_CLOSED** | The socket is no longer functional. The IRP will be completed with failure status. The WSK application must call the [*WskCloseSocket*](nc-wsk-pfn_wsk_close_socket.md) function to close the socket as soon as possible. |
| **STATUS_NOT_SUPPORTED** | A specified flag is not supported by the underlying network transport. |
| **Other status codes** | An error occurred. The IRP will be completed with failure status. |

## -remarks

A WSK application can call the **WskSendEx** function only on a connection-oriented or stream socket that has been previously connected to a remote transport address. A connection-oriented socket is connected to a remote transport address by one of the following methods:

- The WSK application connects the socket by calling the [*WskConnect*](nc-wsk-pfn_wsk_connect.md) function.
- The WSK application creates, binds, and connects the socket by calling the [*WskSocketConnect*](nc-wsk-pfn_wsk_socket_connect.md) function.
- The WSK subsystem connects the socket when the WSK application accepts an incoming connection request on a listening socket.

If the **WskSendEx** function returns STATUS_PENDING, the MDL chain that is described in the [**WSK_BUF**](ns-wsk-_wsk_buf.md) structure that is pointed to by the *Buffer* parameter must remain locked in memory until the IRP is completed.

The WSK subsystem does not perform any buffering of data when it sends data over a socket. Therefore, a call to the **WskSendEx** function will not be completed by the WSK subsystem until all of the data has actually been sent.

## -see-also

[**WSK_BUF**](ns-wsk-_wsk_buf.md)

[**WSK_PROVIDER_CONNECTION_DISPATCH**](ns-wsk-_wsk_provider_connection_dispatch.md)

[**WSK_PROVIDER_STREAM_DISPATCH**](ns-wsk-_wsk_provider_stream_dispatch.md)

[**WSK_SOCKET**](ns-wsk-_wsk_socket.md)

[*WskCloseSocket*](nc-wsk-pfn_wsk_close_socket.md)

[**WskReceiveEx**](nc-wsk-pfn_wsk_receive_ex.md)

[*WskReceiveExEvent*](nc-wsk-pfn_wsk_receive_ex_event.md)