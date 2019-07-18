---
UID: NC:wsk.PFN_WSK_SOCKET
title: PFN_WSK_SOCKET (wsk.h)
description: The WskSocket function creates a new socket and returns a pointer to the associated socket object.
old-location: netvista\wsksocket.htm
tech.root: netvista
ms.assetid: fddfd724-c3ba-4908-a60f-70c4934efb49
ms.date: 05/02/2018
ms.keywords: PFN_WSK_SOCKET, PFN_WSK_SOCKET callback, WskSocket, WskSocket callback function [Network Drivers Starting with Windows Vista], netvista.wsksocket, wsk/WskSocket, wskref_37c59d39-d8fd-4e3f-9f69-c0874e1801ed.xml
ms.topic: callback
f1_keywords:
 - "wsk/WskSocket"
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
- WskSocket
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_WSK_SOCKET callback function


## -description


The 
  <b>WskSocket</b> function creates a new socket and returns a pointer to the associated socket object.


## -parameters




### -param Client [in]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wsk-client">WSK_CLIENT</a> structure that was returned through
     the 
     <i>WskProviderNpi</i> parameter of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nf-wsk-wskcaptureprovidernpi">
     WskCaptureProviderNPI</a> function.


### -param AddressFamily [in]

The address family for the socket that is being created. For more information about supported
     address families, see 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt808757(v=vs.85)">WSK Address Families</a>.


### -param SocketType [in]

The type of socket that is being created. The following socket types are supported:
     





#### SOCK_STREAM

Supports reliable connection-oriented byte stream communication.



#### SOCK_DGRAM

Supports unreliable connectionless datagram communication.



#### SOCK_RAW

Supports raw access to the transport protocol.

For more information about the socket types that are supported for each supported address family, see     
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt808757(v=vs.85)">WSK Address Families</a>.


### -param Protocol [in]

The transport protocol for the socket that is being created. For more information about the
     protocols that are supported for each supported address family, see 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt808757(v=vs.85)">WSK Address Families</a>.


### -param Flags [in]

A flag that specifies the WSK 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/winsock-kernel-socket-categories">socket category</a> for the
     socket that is being created. This parameter can be one of the following flags:
     





#### WSK_FLAG_BASIC_SOCKET

A basic socket will be created that can be used only to get and set transport stack socket
       options or to perform socket I/O control operations.



#### WSK_FLAG_LISTEN_SOCKET

A listening socket will be created that can be used to listen for incoming connections from
       remote transport addresses.



#### WSK_FLAG_DATAGRAM_SOCKET

A datagram socket will be created that can be used to send and receive datagrams.



#### WSK_FLAG_CONNECTION_SOCKET

A connection-oriented socket will be created that can be used to send and receive network data
       over a connection.



#### WSK_FLAG_STREAM_SOCKET

A stream socket will be created that can either be used to listen for incoming connections from remote transport addresses, or send and receive network data over a connection.

If a WSK application does not specify any of the preceding flags, 
     <b>WskSocket</b> creates a basic socket.


### -param SocketContext [in, optional]

A pointer to a caller-supplied context for the socket that is being created. The WSK subsystem
     passes this pointer to the socket's event callback functions. The context information is opaque to the
     WSK subsystem and must be stored in non-paged memory. If the WSK application will not be enabling any
     event callback functions on the new socket, it should set this pointer to <b>NULL</b>. For a basic socket, this
     pointer should always be <b>NULL</b>.


### -param *Dispatch [in, optional]

A pointer to a constant client dispatch structure. This structure is a dispatch table that
     contains pointers to the event callback functions for the new socket. Depending on the WSK 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/winsock-kernel-socket-categories">socket category</a> of the socket
     (as specified by the 
     <i>Flags</i> parameter), this parameter is a pointer to one of the following structures.
     

<table>
<tr>
<th>Flag</th>
<th>Dispatch table structure</th>
</tr>
<tr>
<td>
WSK_FLAG_LISTEN_SOCKET

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_client_listen_dispatch">WSK_CLIENT_LISTEN_DISPATCH</a>


</td>
</tr>
<tr>
<td>
WSK_FLAG_DATAGRAM_SOCKET

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_client_datagram_dispatch">
         WSK_CLIENT_DATAGRAM_DISPATCH</a>


</td>
</tr>
<tr>
<td>
WSK_FLAG_CONNECTION_SOCKET

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_client_connection_dispatch">
         WSK_CLIENT_CONNECTION_DISPATCH</a>


</td>
</tr>
<tr>
<td>
WSK_FLAG_STREAM_SOCKET

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_client_stream_dispatch">WSK_CLIENT_STREAM_DISPATCH</a>


</td>
</tr>
</table>
 

If the WSK application will not be enabling all of the event callback functions for the new socket,
     it should set the pointers in the dispatch table to <b>NULL</b> for those event callback functions that it does
     not enable. If the WSK application will not be enabling any event callback functions on the new socket,
     it should set the 
     <i>Dispatch</i> pointer to <b>NULL</b>. For a basic socket, this pointer should always be <b>NULL</b>.


### -param OwningProcess [in, optional]

A pointer to the process from which the WSK subsystem will retrieve the security context to use
     when it binds the socket. The WSK subsystem uses the security context to determine whether the local
     transport address can be shared if that address is already in use. To specify the current process, a WSK
     application sets this pointer to <b>NULL</b>.


### -param OwningThread [in, optional]

A pointer to a specific thread from which the WSK subsystem will retrieve the security context to
     use when it binds the socket. The WSK subsystem uses the security context to determine whether the local
     transport address can be shared if that address is already in use. If a WSK application does not need to
     specify a specific thread, it sets this pointer to <b>NULL</b>.


### -param SecurityDescriptor [in, optional]

A pointer to a SECURITY_DESCRIPTOR structure that specifies the security descriptor to apply to
     the socket that is being created. The security descriptor controls the sharing of the local transport
     address to which the socket is bound. If a WSK application specifies a non-<b>NULL</b> pointer, it must specify
     a pointer to a cached copy of a security descriptor that was obtained by calling the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_control_client">WskControlClient</a> function with the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wsk-cache-sd">WSK_CACHE_SD</a> control code. To specify a
     default security descriptor that does not allow sharing of the local transport address, a WSK
     application sets 
     <i>SecurityDescriptor</i> to <b>NULL</b>.
     

For more information about the SECURITY_DESCRIPTOR structure, see the reference page for
     SECURITY_DESCRIPTOR in the Microsoft Windows SDK documentation.


### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the creation of the
     new socket asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
     Kernel Functions</a>.


## -returns



<b>WskSocket</b> returns one of the following NTSTATUS codes:

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
The new socket was successfully created. The IRP will be completed with success status.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The WSK subsystem could not create the socket immediately. The WSK subsystem will complete the
       IRP after it has created the new socket. The status of the socket creation will be returned in the 
       <b>IoStatus.Status</b> field of the IRP.

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



If the IRP is completed with success status, the 
    <b>IoStatus.Information</b> field of the IRP contains a pointer to a socket object structure (
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a>) for the new socket.

A WSK application can obtain a list of available transport protocols by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_control_client">WskControlClient</a> function with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wsk-transport-list-query">WSK_TRANSPORT_LIST_QUERY</a> control
    code. 
    <b>WskControlClient</b> returns a list of 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_transport">WSK_TRANSPORT</a> structures that contains all of
    the valid combinations of the 
    <i>AddressFamily</i>, 
    <i>SocketType</i>, and 
    <i>Protocol</i> parameters.

When a WSK application successfully creates a new socket, all of the event callback functions on the
    new socket are disabled by default. For more information about enabling any of the new socket's event
    callback functions, see 
    <a href="https://docs.microsoft.com/windows/desktop/api/evntprov/nc-evntprov-penablecallback">Enabling and
    Disabling Event Callback Functions</a>.

If a WSK application specifies a non-<b>NULL</b> pointer for the 
    <i>SecurityDescriptor</i> parameter, it must not release the cached security descriptor until after the
    IRP is completed.

The WSK subsystem allocates the memory for the socket object structure (WSK_SOCKET) for the new socket
    on behalf of the WSK application. The WSK subsystem deallocates this memory when the socket is
    closed.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wsk-client">WSK_CLIENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_client_connection_dispatch">
   WSK_CLIENT_CONNECTION_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_client_datagram_dispatch">WSK_CLIENT_DATAGRAM_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_client_listen_dispatch">WSK_CLIENT_LISTEN_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_client_stream_dispatch">WSK_CLIENT_STREAM_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_provider_dispatch">WSK_PROVIDER_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_provider_npi">WSK_PROVIDER_NPI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nf-wsk-wskcaptureprovidernpi">WskCaptureProviderNPI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_control_client">WskControlClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_socket_connect">WskSocketConnect</a>
 

 

