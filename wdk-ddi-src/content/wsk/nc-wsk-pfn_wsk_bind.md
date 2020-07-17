---
UID: NC:wsk.PFN_WSK_BIND
title: PFN_WSK_BIND (wsk.h)
description: The WskBind function binds a socket to a local transport address.
old-location: netvista\wskbind.htm
tech.root: netvista
ms.assetid: 520b02d0-a078-4af9-93a3-4fee5bbfee99
ms.date: 05/02/2018
keywords: ["PFN_WSK_BIND callback function"]
ms.keywords: PFN_WSK_BIND, PFN_WSK_BIND callback, WskBind, WskBind callback function [Network Drivers Starting with Windows Vista], netvista.wskbind, wsk/WskBind, wskref_5d411257-ce57-4331-913a-c195e71a1138.xml
f1_keywords:
 - "wsk/WskBind"
 - "WskBind"
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
- WskBind
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_WSK_BIND callback function


## -description


The 
  <b>WskBind</b> function binds a socket to a local transport address.


## -parameters




### -param Socket [in]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a> structure that specifies the socket
     object for the socket that is being bound.


### -param LocalAddress [in]

A pointer to a structure that specifies the local transport address to which to bind the socket.
     This pointer must be a pointer to the specific SOCKADDR structure type that corresponds to the address
     family that the WSK application specified when it created the socket.


### -param Flags

This parameter is reserved for system use. A WSK application must set this parameter to
     zero.


### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the bind operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
     Kernel Functions</a>.


## -returns



<b>WskBind</b> returns one of the following NTSTATUS codes:

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
The socket was successfully bound to the local transport address. The IRP will be completed with
       success status.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The WSK subsystem could not bind the socket immediately. The WSK subsystem will complete the IRP
       after it has bound the socket to the local transport address. The status of the bind operation will be
       returned in the 
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



For a listening socket, calling the 
    <b>WskBind</b> function prepares the socket to listen for incoming connection requests on the specified
    local transport address. If a WSK application specifies a local wildcard address, the socket will listen
    for incoming connection requests on all local transport addresses.

For a datagram socket, calling the 
    <b>WskBind</b> function prepares the socket to send and receive datagrams on the specified local transport
    address. If a WSK application specifies a local wildcard address, the socket will receive datagrams on
    all local transport addresses and will send datagrams from the appropriate local transport address that
    is determined by the system's routing information.

For a connection-oriented socket, calling the 
    <b>WskBind</b> function binds the socket to the specified local transport address. 
    <b>WskBind</b> must be called prior to calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_connect">WskConnect</a> function. If a WSK application
    specifies a local wildcard address, the network stack binds the socket to the appropriate local transport
    address when the application calls 
    <b>WskConnect</b> to connect the socket to a remote transport address. In such a situation, the local
    transport address is determined by the system's routing information.

For a stream socket, calling the <b>WskBind</b> function binds the socket to the specified local transport address. If a WSK application specifies a local wildcard address, the network stack binds the socket to an available local transport address. <b>WskBind</b> must be called prior to calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_listen">WskListen</a> or the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_connect">WskConnect</a> functions.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ws2def/ns-ws2def-sockaddr">SOCKADDR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_connection_dispatch">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_datagram_dispatch">
   WSK_PROVIDER_DATAGRAM_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_listen_dispatch">WSK_PROVIDER_LISTEN_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_stream_dispatch">WSK_PROVIDER_STREAM_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_connect">WskConnect</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket">WskSocket</a>
 

 

