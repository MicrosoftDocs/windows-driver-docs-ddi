---
UID: NC:wsk.PFN_WSK_SOCKET
title: PFN_WSK_SOCKET
author: windows-driver-content
description: The WskSocket function creates a new socket and returns a pointer to the associated socket object.
old-location: netvista\wsksocket.htm
old-project: netvista
ms.assetid: fddfd724-c3ba-4908-a60f-70c4934efb49
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.wsksocket, WskSocket callback function [Network Drivers Starting with Windows Vista], WskSocket, PFN_WSK_SOCKET, PFN_WSK_SOCKET, wsk/WskSocket, wskref_37c59d39-d8fd-4e3f-9f69-c0874e1801ed.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	wsk.h
apiname:
-	WskSocket
product: Windows
targetos: Windows
req.typenames: WNODE_HEADER, *PWNODE_HEADER
req.product: Windows 10 or later.
---

# PFN_WSK_SOCKET callback


## -description


The 
  <b>WskSocket</b> function creates a new socket and returns a pointer to the associated socket object.


## -prototype


````
PFN_WSK_SOCKET WskSocket;

NTSTATUS WSKAPI * WskSocket(
  _In_           PWSK_CLIENT          Client,
  _In_           ADDRESS_FAMILY       AddressFamily,
  _In_           USHORT               SocketType,
  _In_           ULONG                Protocol,
  _In_           ULONG                Flags,
  _In_opt_       PVOID                SocketContext,
  _In_opt_ const VOID                 *Dispatch,
  _In_opt_       PEPROCESS            OwningProcess,
  _In_opt_       PETHREAD             OwningThread,
  _In_opt_       PSECURITY_DESCRIPTOR SecurityDescriptor,
  _Inout_        PIRP                 Irp
)
{ ... }
````


## -parameters




#### - Client [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571155">WSK_CLIENT</a> structure that was returned through
     the 
     <i>WskProviderNpi</i> parameter of the 
     <mshelp:link keywords="netvista.wskcaptureprovidernpi" tabindex="0"><b>
     WskCaptureProviderNPI</b></mshelp:link> function.


#### - AddressFamily [in]

The address family for the socket that is being created. For more information about supported
     address families, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571151">WSK Address Families</a>.


#### - SocketType [in]

The type of socket that is being created. The following socket types are supported:
     



For more information about the socket types that are supported for each supported address family, see
     
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571151">WSK Address Families</a>.


#### SOCK_STREAM

Supports reliable connection-oriented byte stream communication.


#### SOCK_DGRAM

Supports unreliable connectionless datagram communication.


#### SOCK_RAW

Supports raw access to the transport protocol.


#### - Protocol [in]

The transport protocol for the socket that is being created. For more information about the
     protocols that are supported for each supported address family, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571151">WSK Address Families</a>.


#### - Flags [in]

A flag that specifies the WSK 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/winsock-kernel-socket-categories">socket category</a> for the
     socket that is being created. This parameter can be one of the following flags:
     



If a WSK application does not specify any of the preceding flags, 
     <b>WskSocket</b> creates a basic socket.


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


#### - SocketContext [in, optional]

A pointer to a caller-supplied context for the socket that is being created. The WSK subsystem
     passes this pointer to the socket's event callback functions. The context information is opaque to the
     WSK subsystem and must be stored in non-paged memory. If the WSK application will not be enabling any
     event callback functions on the new socket, it should set this pointer to <b>NULL</b>. For a basic socket, this
     pointer should always be <b>NULL</b>.


#### - *Dispatch [in, optional]

A pointer to a constant client dispatch structure. This structure is a dispatch table that
     contains pointers to the event callback functions for the new socket. Depending on the WSK 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/winsock-kernel-socket-categories">socket category</a> of the socket
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

<a href="..\wsk\ns-wsk-_wsk_client_listen_dispatch.md">WSK_CLIENT_LISTEN_DISPATCH</a>


</td>
</tr>
<tr>
<td>
WSK_FLAG_DATAGRAM_SOCKET

</td>
<td>

<mshelp:link keywords="netvista.wsk_client_datagram_dispatch" tabindex="0"><b>
         WSK_CLIENT_DATAGRAM_DISPATCH</b></mshelp:link>


</td>
</tr>
<tr>
<td>
WSK_FLAG_CONNECTION_SOCKET

</td>
<td>

<mshelp:link keywords="netvista.wsk_client_connection_dispatch" tabindex="0"><b>
         WSK_CLIENT_CONNECTION_DISPATCH</b></mshelp:link>


</td>
</tr>
<tr>
<td>
WSK_FLAG_STREAM_SOCKET

</td>
<td>

<a href="..\wsk\ns-wsk-_wsk_client_stream_dispatch.md">WSK_CLIENT_STREAM_DISPATCH</a>


</td>
</tr>
</table> 

If the WSK application will not be enabling all of the event callback functions for the new socket,
     it should set the pointers in the dispatch table to <b>NULL</b> for those event callback functions that it does
     not enable. If the WSK application will not be enabling any event callback functions on the new socket,
     it should set the 
     <i>Dispatch</i> pointer to <b>NULL</b>. For a basic socket, this pointer should always be <b>NULL</b>.


#### - OwningProcess [in, optional]

A pointer to the process from which the WSK subsystem will retrieve the security context to use
     when it binds the socket. The WSK subsystem uses the security context to determine whether the local
     transport address can be shared if that address is already in use. To specify the current process, a WSK
     application sets this pointer to <b>NULL</b>.


#### - OwningThread [in, optional]

A pointer to a specific thread from which the WSK subsystem will retrieve the security context to
     use when it binds the socket. The WSK subsystem uses the security context to determine whether the local
     transport address can be shared if that address is already in use. If a WSK application does not need to
     specify a specific thread, it sets this pointer to <b>NULL</b>.


#### - SecurityDescriptor [in, optional]

A pointer to a SECURITY_DESCRIPTOR structure that specifies the security descriptor to apply to
     the socket that is being created. The security descriptor controls the sharing of the local transport
     address to which the socket is bound. If a WSK application specifies a non-<b>NULL</b> pointer, it must specify
     a pointer to a cached copy of a security descriptor that was obtained by calling the 
     <a href="..\wsk\nc-wsk-pfn_wsk_control_client.md">WskControlClient</a> function with the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571154">WSK_CACHE_SD</a> control code. To specify a
     default security descriptor that does not allow sharing of the local transport address, a WSK
     application sets 
     <i>SecurityDescriptor</i> to <b>NULL</b>.
     

For more information about the SECURITY_DESCRIPTOR structure, see the reference page for
     SECURITY_DESCRIPTOR in the Microsoft Windows SDK documentation.


#### - Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the creation of the
     new socket asynchronously. For more information about using IRPs with WSK functions, see 
     <mshelp:link keywords="netvista.using_irps_with_winsock_kernel_functions" tabindex="0">Using IRPs with Winsock
     Kernel Functions</mshelp:link>.


#### - Dispatch [in, optional]

A pointer to a constant client dispatch structure. This structure is a dispatch table that
     contains pointers to the event callback functions for the new socket. Depending on the WSK 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/winsock-kernel-socket-categories">socket category</a> of the socket
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

<a href="..\wsk\ns-wsk-_wsk_client_listen_dispatch.md">WSK_CLIENT_LISTEN_DISPATCH</a>


</td>
</tr>
<tr>
<td>
WSK_FLAG_DATAGRAM_SOCKET

</td>
<td>

<mshelp:link keywords="netvista.wsk_client_datagram_dispatch" tabindex="0"><b>
         WSK_CLIENT_DATAGRAM_DISPATCH</b></mshelp:link>


</td>
</tr>
<tr>
<td>
WSK_FLAG_CONNECTION_SOCKET

</td>
<td>

<mshelp:link keywords="netvista.wsk_client_connection_dispatch" tabindex="0"><b>
         WSK_CLIENT_CONNECTION_DISPATCH</b></mshelp:link>


</td>
</tr>
<tr>
<td>
WSK_FLAG_STREAM_SOCKET

</td>
<td>

<a href="..\wsk\ns-wsk-_wsk_client_stream_dispatch.md">WSK_CLIENT_STREAM_DISPATCH</a>


</td>
</tr>
</table> 

If the WSK application will not be enabling all of the event callback functions for the new socket,
     it should set the pointers in the dispatch table to <b>NULL</b> for those event callback functions that it does
     not enable. If the WSK application will not be enabling any event callback functions on the new socket,
     it should set the 
     <i>Dispatch</i> pointer to <b>NULL</b>. For a basic socket, this pointer should always be <b>NULL</b>.


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
    <a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a>) for the new socket.

A WSK application can obtain a list of available transport protocols by calling the 
    <a href="..\wsk\nc-wsk-pfn_wsk_control_client.md">WskControlClient</a> function with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571195">WSK_TRANSPORT_LIST_QUERY</a> control
    code. 
    <b>WskControlClient</b> returns a list of 
    <a href="..\wsk\ns-wsk-_wsk_transport.md">WSK_TRANSPORT</a> structures that contains all of
    the valid combinations of the 
    <i>AddressFamily</i>, 
    <i>SocketType</i>, and 
    <i>Protocol</i> parameters.

When a WSK application successfully creates a new socket, all of the event callback functions on the
    new socket are disabled by default. For more information about enabling any of the new socket's event
    callback functions, see 
    <mshelp:link keywords="netvista.enabling_and_disabling_event_callback_functions" tabindex="0">Enabling and
    Disabling Event Callback Functions</mshelp:link>.

If a WSK application specifies a non-<b>NULL</b> pointer for the 
    <i>SecurityDescriptor</i> parameter, it must not release the cached security descriptor until after the
    IRP is completed.

The WSK subsystem allocates the memory for the socket object structure (WSK_SOCKET) for the new socket
    on behalf of the WSK application. The WSK subsystem deallocates this memory when the socket is
    closed.



## -see-also

<mshelp:link keywords="netvista.wsk_client_connection_dispatch" tabindex="0"><b>
   WSK_CLIENT_CONNECTION_DISPATCH</b></mshelp:link>

<a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a>

<a href="..\wsk\ns-wsk-_wsk_client_stream_dispatch.md">WSK_CLIENT_STREAM_DISPATCH</a>

<a href="..\wsk\ns-wsk-_wsk_client_listen_dispatch.md">WSK_CLIENT_LISTEN_DISPATCH</a>

<a href="..\wsk\ns-wsk-_wsk_client_datagram_dispatch.md">WSK_CLIENT_DATAGRAM_DISPATCH</a>

<a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a>

<a href="..\wsk\ns-wsk-_wsk_provider_npi.md">WSK_PROVIDER_NPI</a>

<a href="..\wsk\ns-wsk-_wsk_provider_dispatch.md">WSK_PROVIDER_DISPATCH</a>

<a href="..\wsk\nc-wsk-pfn_wsk_control_client.md">WskControlClient</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff571155">WSK_CLIENT</a>

<a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a>

<a href="..\wsk\nf-wsk-wskcaptureprovidernpi.md">WskCaptureProviderNPI</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_SOCKET callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

