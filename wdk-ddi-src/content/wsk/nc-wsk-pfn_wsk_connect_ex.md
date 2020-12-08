---
UID: NC:wsk.PFN_WSK_CONNECT_EX
title: PFN_WSK_CONNECT_EX (wsk.h)
description: The WskConnectEx function connects a connection-oriented or stream socket to a remote transport address.WskConnectEx is similar to WskConnect except that it can also optionally send a buffer of data during or after connection synchronization.
old-location: netvista\wskconnectex.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["PFN_WSK_CONNECT_EX callback function"]
ms.keywords: PFN_WSK_CONNECT_EX, PFN_WSK_CONNECT_EX callback, WskConnectEx, WskConnectEx callback function [Network Drivers Starting with Windows Vista], netvista.wskconnectex, wsk/WskConnectEx
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1703
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFN_WSK_CONNECT_EX
 - wsk/PFN_WSK_CONNECT_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wsk.h
api_name:
 - WskConnectEx
---

# PFN_WSK_CONNECT_EX callback function


## -description

The 
  <b>WskConnectEx</b> function connects a connection-oriented or stream socket to a remote transport address.

<b>WskConnectEx</b> is similar to <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_connect">WskConnect</a>
  except that it can also optionally send a buffer of data during or after connection synchronization.

## -parameters

### -param Socket 

[in]
A pointer to a 
     <a href="/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a> structure that specifies the socket
     object for the socket that is being connected to a remote transport address.

### -param RemoteAddress 

[in]
A pointer to a structure that specifies the remote transport address to which to connect the
     socket. This pointer must be a pointer to the specific <a href="/windows/win32/api/ws2def/ns-ws2def-sockaddr">SOCKADDR</a> structure type that corresponds to the
     address family that the WSK application specified when it created the socket.

### -param Buffer 

[in, optional]
A pointer to a <a href="/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_buf">WSK_BUF</a> structure, which contains the data to send during or after connection synchronization. The maximum allowed size in bytes is 65,535.

### -param Flags

This parameter is reserved for system use. A WSK application must set this parameter to
     zero.

### -param Irp 

[in, out]
A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the connect operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
     Kernel Functions</a>.

## -returns

<b>WskConnectEx</b> returns one of the following NTSTATUS codes:

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
The socket was successfully connected to the remote transport address. The IRP will be completed
       with success status.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The WSK subsystem could not connect the socket immediately. The WSK subsystem will complete the
       IRP after it has connected the socket to the remote transport address. The status of the connect
       operation will be returned in the 
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
       <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a> function to close the
       socket as soon as possible.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The WSK application attempted to pass a flag in to the <i>Flags</i> parameter (as no valid flags are currently defined for <b>WskConnectEx</b>, this is not allowed).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The WSK application attempted to pass in a buffer larger than 65,535 bytes to the <i>Buffer</i> parameter.

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

A WSK application can create, bind, and connect a connection-oriented socket in a single function call
    by calling the 
    <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket_connect">WskSocketConnect</a> function rather than
    calling the 
    <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket">WskSocket</a> function, the 
    <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_bind">WskBind</a> function, and then the 
    <b>WskConnectEx</b> function. We recommend calling the 
    <b>WskSocketConnect</b> function unless the WSK application needs to set a socket option or issue an I/O
    control operation before binding or connecting the socket.

A WSK application can call the 
    <b>WskConnectEx</b> function only on a connection-oriented or stream socket that the application previously bound to a
    local transport address by calling the 
    <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_bind">WskBind</a> function.

For stream sockets, once <b>WskConnectEx</b> is successfully called on a stream socket, the socket is committed to a connection-oriented flow and may no longer call listening socket functions.

If the <i>Buffer</i> parameter is used, the caller can free the MDL in its <a href="/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_buf">WSK_BUF</a> structure as soon as the connect request is complete.

Before calling <b>WskConnectEx</b> with a provided send buffer, if the WSK application sets the <b>TCP_FASTOPEN</b> option on a WSK socket via the <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_control_socket">WskControlSocket</a> function the system will optionally send some or all of the data in a SYN packet. For more information, see the <b>TCP Fastopen</b> option in <a href="/windows/desktop/WinSock/ipproto-tcp-socket-options">IPPROTO_TCP Socket Options</a>.

## -see-also

<a href="/windows/win32/api/ws2def/ns-ws2def-sockaddr">SOCKADDR</a>



<a href="/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_connection_dispatch">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>



<a href="/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_stream_dispatch">
   WSK_PROVIDER_STREAM_DISPATCH</a>



<a href="/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_bind">WskBind</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_control_socket">WskControlSocket</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_disconnect">WskDisconnect</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_disconnect_event">WskDisconnectEvent</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket">WskSocket</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket_connect">WskSocketConnect</a>
