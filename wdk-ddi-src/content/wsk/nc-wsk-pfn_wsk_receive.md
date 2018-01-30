---
UID: NC:wsk.PFN_WSK_RECEIVE
title: PFN_WSK_RECEIVE
author: windows-driver-content
description: The WskReceive function receives data over a connection-oriented or stream socket from a remote transport address.
old-location: netvista\wskreceive.htm
old-project: netvista
ms.assetid: 7fe65842-8ddb-4aca-931f-03b35dd2b039
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.wskreceive, WskReceive callback function [Network Drivers Starting with Windows Vista], WskReceive, PFN_WSK_RECEIVE, PFN_WSK_RECEIVE, wsk/WskReceive, wskref_7a0473b3-5687-44e8-b505-a346e9546807.xml
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
-	WskReceive
product: Windows
targetos: Windows
req.typenames: "*PWNODE_HEADER, WNODE_HEADER"
req.product: Windows 10 or later.
---

# PFN_WSK_RECEIVE callback


## -description


The 
  <b>WskReceive</b> function receives data over a connection-oriented or stream socket from a remote transport
  address.


## -prototype


````
PFN_WSK_RECEIVE WskReceive;

NTSTATUS WSKAPI * WskReceive(
  _In_    PWSK_SOCKET Socket,
  _In_    PWSK_BUF    Buffer,
  _In_    ULONG       Flags,
  _Inout_ PIRP        Irp
)
{ ... }
````


## -parameters




### -param Socket [in]

A pointer to a 
     <a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a> structure that specifies the socket
     object for the socket from which to receive the data.


### -param Buffer [in]

A pointer to an initialized 
     <a href="..\wsk\ns-wsk-_wsk_buf.md">WSK_BUF</a> structure that describes the data buffer
     that receives the data from the socket.


### -param Flags [in]

A ULONG value that contains a bitwise OR of a combination of the following flags:
     



The WSK_FLAG_WAITALL and WSK_FLAG_DRAIN flags are mutually exclusive. A WSK application should not
     specify both of these flags at the same time.


#### WSK_FLAG_WAITALL

Wait until the data buffer is completely filled. If this flag is specified, the IRP specified in
       the 
       <i>Irp</i> parameter will not be completed until one of the following events occurs:
       
<ul>
<li>
The data buffer that is described by the WSK_BUF structure that is pointed to by the 
         <i>Buffer</i> parameter is completely filled.

</li>
<li>
The connection is gracefully disconnected by the remote sender.

</li>
<li>
The connection is abortively disconnected by either the WSK application or by the remote
         sender.

</li>
<li>
The specified IRP is canceled.

</li>
</ul>This flag is supported by the Microsoft TCP/IP transport protocol. This flag might not be supported
       by other transport protocols.


#### WSK_FLAG_DRAIN

Wait until the socket is disconnected, discarding any data that is received on the socket. If
       this flag is specified, the specified IRP will not be completed until one of the following events
       occurs:
       
<ul>
<li>
The connection is gracefully disconnected by the remote sender.

</li>
<li>
The connection is abortively disconnected by either the WSK application or by the remote
         sender.

</li>
<li>
The specified IRP is canceled.

</li>
</ul>Any received data is discarded by the WSK subsystem. No received data will be copied into the data
       buffer. The 
       <i>Buffer</i> parameter is still required when this flag is specified, but the length of the buffer
       that is described by the WSK_BUF structure must be zero.

This flag is supported by the Microsoft TCP/IP transport protocol. This flag might not be supported
       by other transport protocols.


### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the receive operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <mshelp:link keywords="netvista.using_irps_with_winsock_kernel_functions" tabindex="0">Using IRPs with Winsock
     Kernel Functions</mshelp:link>.


## -returns


<b>WskReceive</b> returns one of the following NTSTATUS codes:
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
Data was successfully received from the socket. The IRP will be completed with success status.
       The 
       <b>IoStatus.Information</b> field of the IRP contains the number of bytes that were received.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The WSK subsystem could not receive the data from the socket immediately. The WSK subsystem will
       complete the IRP after it has received the data from the socket. The status of the receive operation
       will be returned in the 
       <b>IoStatus.Status</b> field of the IRP. If the operation succeeds, the 
       <b>IoStatus.Information</b> field of the IRP will contain the number of bytes that were
       received.

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
       <a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a> function to close the
       socket as soon as possible.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
A specified flag is not supported by the underlying network transport.

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
    <b>WskReceive</b> function only on a connection-oriented or stream socket that has been previously connected to a
    remote transport address. A connection-oriented socket is connected to a remote transport address by one
    of the following methods:
<ul>
<li>
The WSK application connects the socket by calling the 
      <a href="..\wsk\nc-wsk-pfn_wsk_connect.md">WskConnect</a> function.

</li>
<li>
The WSK application creates, binds, and connects the socket by calling the 
      <a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a> function.

</li>
<li>
The WSK subsystem connects the socket when the WSK application accepts an incoming connection
      request on a listening socket.

</li>
</ul>If a WSK application's 
    <a href="..\wsk\nc-wsk-pfn_wsk_receive_event.md">WskReceiveEvent</a> event callback function is
    enabled on a connection-oriented socket and the application also has a pending call to the 
    <b>WskReceive</b> function on the same connection-oriented socket, then, when data arrives, the pending
    call to the 
    <b>WskReceive</b> function will take precedence over the 
    <i>WskReceiveEvent</i> event callback function. The WSK subsystem calls the application's 
    <i>WskReceiveEvent</i> event callback function only if there are no IRPs queued from pending calls to the 
    <b>WskReceive</b> function. However, a WSK application should not assume that the WSK subsystem will not
    call the application's 
    <i>WskReceiveEvent</i> event callback function for a connection-oriented socket that has a pending call to
    the 
    <b>WskReceive</b> function. Race conditions exist where the WSK subsystem could still call the WSK
    application's 
    <i>WskReceiveEvent</i> event callback function for the socket. The only way for a WSK application to
    ensure that the WSK subsystem will not call the application's 
    <i>WskReceiveEvent</i> event callback function for a connection-oriented socket is to disable the
    application's 
    <i>WskReceiveEvent</i> event callback function on the socket.

A WSK application can call the 
    <b>WskReceive</b> function with a zero length specified in the 
    <b>Length</b> member of the 
    <a href="..\wsk\ns-wsk-_wsk_buf.md">WSK_BUF</a> structure that is pointed to by the 
    <i>Buffer</i> parameter. Specifying a zero length in this member is useful in the following
    situations:
<ul>
<li>
When re-enabling the 
      <i>WskReceiveEvent</i> event callback function for a socket after the 
      <i>WskReceiveEvent</i> event callback function previously returned STATUS_DATA_NOT_ACCEPTED

</li>
<li>
When specifying the WSK_FLAG_DRAIN flag to discard any additional data that is received on the
      socket

</li>
</ul>If the 
    <b>WskReceive</b> function returns STATUS_PENDING, the MDL chain that is described in the WSK_BUF
    structure that is pointed to by the 
    <i>Buffer</i> parameter must remain locked in memory until the IRP is completed.



## -see-also

<a href="..\wsk\nc-wsk-pfn_wsk_send.md">WskSend</a>

<mshelp:link keywords="netvista.wsk_provider_connection_dispatch" tabindex="0"><b>
   WSK_PROVIDER_CONNECTION_DISPATCH</b></mshelp:link>

<a href="..\wsk\ns-wsk-_wsk_provider_stream_dispatch.md">WSK_PROVIDER_STREAM_DISPATCH</a>

<a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a>

<a href="..\wsk\ns-wsk-_wsk_buf.md">WSK_BUF</a>

<a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a>

<a href="..\wsk\nc-wsk-pfn_wsk_receive_event.md">WskReceiveEvent</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_RECEIVE callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

