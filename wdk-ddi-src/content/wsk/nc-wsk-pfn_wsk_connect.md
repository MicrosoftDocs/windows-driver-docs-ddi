---
UID: NC:wsk.PFN_WSK_CONNECT
title: PFN_WSK_CONNECT (wsk.h)
description: The WskConnect function connects a connection-oriented or stream socket to a remote transport address.
old-location: netvista\wskconnect.htm
tech.root: netvista
ms.assetid: 66942ba4-40f9-4fdc-97f3-859309cd870d
ms.date: 05/02/2018
ms.keywords: PFN_WSK_CONNECT, PFN_WSK_CONNECT callback, WskConnect, WskConnect callback function [Network Drivers Starting with Windows Vista], netvista.wskconnect, wsk/WskConnect, wskref_16a15402-b34a-40b7-87a7-881d422e0d1c.xml
ms.topic: callback
f1_keywords:
 - "wsk/WskConnect"
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- wsk.h
api_name:
- WskConnect
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_WSK_CONNECT callback function


## -description


The 
  <b>WskConnect</b> function connects a connection-oriented or stream socket to a remote transport address.


## -parameters




### -param Socket [in]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a> structure that specifies the socket
     object for the socket that is being connected to a remote transport address.


### -param RemoteAddress [in]

A pointer to a structure that specifies the remote transport address to which to connect the
     socket. This pointer must be a pointer to the specific SOCKADDR structure type that corresponds to the
     address family that the WSK application specified when it created the socket.


### -param Flags

This parameter is reserved for system use. A WSK application must set this parameter to
     zero.


### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the connect operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
     Kernel Functions</a>.


## -returns



<b>WskConnect</b> returns one of the following NTSTATUS codes:

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
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a> function to close the
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
    <b>WskConnect</b> function only on a connection-oriented or stream socket that the application previously bound to a
    local transport address by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_bind">WskBind</a> function.

For stream sockets, once <b>WskConnect</b> is successfully called on a stream socket, the socket is committed to a connection-oriented flow and may no longer call listening socket functions.

A WSK application can create, bind, and connect a connection-oriented socket in a single function call
    by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_socket_connect">WskSocketConnect</a> function rather than
    calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_socket">WskSocket</a> function, the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_bind">WskBind</a> function, and then the 
    <b>WskConnect</b> function. We recommend calling the 
    <b>WskSocketConnect</b> function unless the WSK application needs to set a socket option or issue an I/O
    control operation before binding or connecting the socket.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ws2def/ns-ws2def-sockaddr">SOCKADDR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_provider_connection_dispatch">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_provider_stream_dispatch">
   WSK_PROVIDER_STREAM_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_bind">WskBind</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_disconnect">WskDisconnect</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_disconnect_event">WskDisconnectEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_socket">WskSocket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_socket_connect">WskSocketConnect</a>
 

 

