---
UID: NC:wsk.PFN_WSK_RECEIVE
title: PFN_WSK_RECEIVE (wsk.h)
description: The WskReceive function receives data over a connection-oriented or stream socket from a remote transport address.
old-location: netvista\wskreceive.htm
tech.root: netvista
ms.assetid: 7fe65842-8ddb-4aca-931f-03b35dd2b039
ms.date: 05/02/2018
keywords: ["PFN_WSK_RECEIVE callback function"]
ms.keywords: PFN_WSK_RECEIVE, PFN_WSK_RECEIVE callback, WskReceive, WskReceive callback function [Network Drivers Starting with Windows Vista], netvista.wskreceive, wsk/WskReceive, wskref_7a0473b3-5687-44e8-b505-a346e9546807.xml
f1_keywords:
 - "wsk/WskReceive"
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
- WskReceive
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_WSK_RECEIVE callback function


## -description


The 
  <b>WskReceive</b> function receives data over a connection-oriented or stream socket from a remote transport
  address.


## -parameters




### -param Socket [in]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a> structure that specifies the socket
     object for the socket from which to receive the data.


### -param Buffer [in]

A pointer to an initialized 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_buf">WSK_BUF</a> structure that describes the data buffer
     that receives the data from the socket.


### -param Flags [in]

A ULONG value that contains a bitwise OR of a combination of the following flags:
     





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
</ul>
This flag is supported by the Microsoft TCP/IP transport protocol. This flag might not be supported
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
</ul>
Any received data is discarded by the WSK subsystem. No received data will be copied into the data
       buffer. The 
       <i>Buffer</i> parameter is still required when this flag is specified, but the length of the buffer
       that is described by the WSK_BUF structure must be zero.

This flag is supported by the Microsoft TCP/IP transport protocol. This flag might not be supported
       by other transport protocols.

The WSK_FLAG_WAITALL and WSK_FLAG_DRAIN flags are mutually exclusive. A WSK application should not
     specify both of these flags at the same time.


### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the receive operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
     Kernel Functions</a>.


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
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a> function to close the
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
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_connect">WskConnect</a> function.

</li>
<li>
The WSK application creates, binds, and connects the socket by calling the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket_connect">WskSocketConnect</a> function.

</li>
<li>
The WSK subsystem connects the socket when the WSK application accepts an incoming connection
      request on a listening socket.

</li>
</ul>
If a WSK application's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_receive_event">WskReceiveEvent</a> event callback function is
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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_buf">WSK_BUF</a> structure that is pointed to by the 
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
</ul>
If the 
    <b>WskReceive</b> function returns STATUS_PENDING, the MDL chain that is described in the WSK_BUF
    structure that is pointed to by the 
    <i>Buffer</i> parameter must remain locked in memory until the IRP is completed.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_buf">WSK_BUF</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_connection_dispatch">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_stream_dispatch">WSK_PROVIDER_STREAM_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_receive_event">WskReceiveEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_send">WskSend</a>
 

 

