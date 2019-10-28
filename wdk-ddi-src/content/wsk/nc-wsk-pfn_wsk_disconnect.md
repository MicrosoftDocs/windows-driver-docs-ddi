---
UID: NC:wsk.PFN_WSK_DISCONNECT
title: PFN_WSK_DISCONNECT (wsk.h)
description: The WskDisconnect function disconnects a connection-oriented or stream socket from a remote transport address.
old-location: netvista\wskdisconnect.htm
tech.root: netvista
ms.assetid: 499ff5d0-2030-472c-8de2-44dcd253d7b9
ms.date: 05/02/2018
ms.keywords: PFN_WSK_DISCONNECT, PFN_WSK_DISCONNECT callback, WskDisconnect, WskDisconnect callback function [Network Drivers Starting with Windows Vista], netvista.wskdisconnect, wsk/WskDisconnect, wskref_0c0dd54e-03d9-4bb6-9040-68f352cfb6ae.xml
ms.topic: callback
f1_keywords:
 - "wsk/WskDisconnect"
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- wsk.h
api_name:
- WskDisconnect
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_WSK_DISCONNECT callback function


## -description


The 
  <b>WskDisconnect</b> function disconnects a connection-oriented or stream socket from a remote transport
  address.


## -parameters




### -param Socket [in]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a> structure that specifies the socket
     object for the socket that is being disconnected.


### -param Buffer [in, optional]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_buf">WSK_BUF</a> structure. This structure describes a data
     buffer that contains data to be transmitted by the WSK subsystem to the remote transport address before
     the socket is disconnected. If there is no such data to be transmitted, the WSK application sets this
     pointer to <b>NULL</b>. If WSK_FLAG_ABORTIVE is specified in the 
     <i>Flags</i> parameter, the 
     <i>Buffer</i> parameter must be <b>NULL</b>.


### -param Flags [in]

A ULONG value that contains the following flag, or zero:
     





#### WSK_FLAG_ABORTIVE

Directs the WSK subsystem to perform an abortive disconnect of the socket. If a WSK application
       does not specify this flag, the WSK subsystem will perform a graceful disconnect of the socket.


### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the disconnect
     operation asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
     Kernel Functions</a>.


## -returns



<b>WskDisconnect</b> returns one of the following NTSTATUS codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The socket was successfully disconnected from the remote transport address. The IRP will be
       completed with success status.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The WSK subsystem could not disconnect the socket immediately. The WSK subsystem will complete
       the IRP after it has disconnected the socket from the remote transport address. The status of the
       disconnect operation will be returned in the 
       <b>IoStatus.Status</b> field of the IRP.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FILE_FORCED_CLOSED</b></dt>
</dl>
</td>
<td width="60%">
The socket is no longer functional. The IRP will be completed with failure status. The WSK
       application must call the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a> function to close the
       socket as soon as possible.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. The IRP will be completed with failure status.

</td>
</tr>
</table>
 




## -remarks



A WSK application can call the 
    <b>WskDisconnect</b> function only on a connection-oriented or stream socket that it previously connected to a
    remote transport address or on a socket that it accepted on a listening socket.

<b>WskDisconnect</b> causes the WSK subsystem to notify the remote transport address, through whatever
    means is appropriate for the underlying transport, that the connection is being disconnected. If the 
    <i>Buffer</i> parameter is non-<b>NULL</b>, the WSK subsystem transmits the data in the buffer to the remote
    transport address before disconnecting the socket.

If a graceful disconnect is performed, the WSK subsystem waits until all outstanding transmit data has
    been sent before disconnecting the socket. After the socket has been disconnected, the WSK application
    cannot send any additional data to the remote transport address. However, the WSK application can still
    receive additional data from the remote transport address until the remote application disconnects its
    end of the socket.

Note that not all transports support half-open connections. If a transport does not support half-open
    connections, the WSK application will not receive any additional data from the remote transport address
    after a graceful disconnect has been performed.

With a graceful disconnect, the IRP is completed only when the disconnect operation is fully completed
    by the transport protocol. For some transport protocols, the IRP might not complete if there is a problem
    transmitting data to the remote transport address. In this situation, the WSK application can recover by
    either calling the 
    <b>WskDisconnect</b> function again and specifying the WSK_FLAG_ABORTIVE flag or by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a> function. In either
    situation, the WSK subsystem will abortively disconnect the socket and force completion of the pending
    IRP.

If an abortive disconnect is performed, the WSK subsystem cancels all in-progress and pending transmit
    operations and does not wait to disconnect the socket. After an abortive disconnect, the WSK application
    cannot send any additional data to the remote transport address or receive any additional data from the
    remote transport address.

A WSK application can completely close the connection by calling the 
    <b>WskCloseSocket</b> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_buf">WSK_BUF</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_connection_dispatch">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_stream_dispatch">WSK_PROVIDER_STREAM_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_connect">WskConnect</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_disconnect_event">WskDisconnectEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket_connect">WskSocketConnect</a>
 

 

