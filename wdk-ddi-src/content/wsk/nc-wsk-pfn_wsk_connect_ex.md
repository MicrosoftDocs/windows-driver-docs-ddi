---
UID: NC:wsk.PFN_WSK_CONNECT_EX
title: PFN_WSK_CONNECT_EX
author: windows-driver-content
description: The WskConnectEx function connects a connection-oriented or stream socket to a remote transport address.WskConnectEx is similar to WskConnect except that it can also optionally send a buffer of data during or after connection synchronization.
old-location: netvista\wskconnectex.htm
old-project: netvista
ms.assetid: 1BC518E9-747C-4406-8A2A-40A3BCB0A3AA
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: PFN_WSK_CONNECT_EX, WskConnectEx, WskConnectEx callback function [Network Drivers Starting with Windows Vista], netvista.wskconnectex, wsk/WskConnectEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wsk.h
api_name:
-	WskConnectEx
product: Windows
targetos: Windows
req.typenames: WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO
req.product: Windows 10 or later.
---

# PFN_WSK_CONNECT_EX callback


## -description


The 
  <b>WskConnectEx</b> function connects a connection-oriented or stream socket to a remote transport address.

<b>WskConnectEx</b> is similar to <a href="..\wsk\nc-wsk-pfn_wsk_connect.md">WskConnect</a>
  except that it can also optionally send a buffer of data during or after connection synchronization.


## -prototype


````
PFN_WSK_CONNECT_EX WskConnectEx;

NTSTATUS WINAPI WskConnectEx(
  _In_       PWSK_SOCKET Socket,
  _In_       PSOCKADDR   RemoteAddress,
  _In_opt_   PWSK_BUF    Buffer,
  _Reserved_ ULONG       Flags,
  _Inout_    PIRP        Irp
)
{ ... }
````


## -parameters




### -param Socket [in]

A pointer to a 
     <a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a> structure that specifies the socket
     object for the socket that is being connected to a remote transport address.


### -param RemoteAddress [in]

A pointer to a structure that specifies the remote transport address to which to connect the
     socket. This pointer must be a pointer to the specific <a href="https://msdn.microsoft.com/library/windows/hardware/ff570822">SOCKADDR</a> structure type that corresponds to the
     address family that the WSK application specified when it created the socket.


### -param Buffer [in, optional]

A pointer to a <a href="..\wsk\ns-wsk-_wsk_buf.md">WSK_BUF</a> structure, which contains the data to send during or after connection synchronization. The maximum allowed size in bytes is 65,535.


### -param Flags

This parameter is reserved for system use. A WSK application must set this parameter to
     zero. 


### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the connect operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
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
       <a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a> function to close the
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
    <a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a> function rather than
    calling the 
    <a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a> function, the 
    <a href="..\wsk\nc-wsk-pfn_wsk_bind.md">WskBind</a> function, and then the 
    <b>WskConnectEx</b> function. We recommend calling the 
    <b>WskSocketConnect</b> function unless the WSK application needs to set a socket option or issue an I/O
    control operation before binding or connecting the socket.

A WSK application can call the 
    <b>WskConnectEx</b> function only on a connection-oriented or stream socket that the application previously bound to a
    local transport address by calling the 
    <a href="..\wsk\nc-wsk-pfn_wsk_bind.md">WskBind</a> function.

For stream sockets, once <b>WskConnectEx</b> is successfully called on a stream socket, the socket is committed to a connection-oriented flow and may no longer call listening socket functions.

If the <i>Buffer</i> parameter is used, the caller can free the MDL in its <a href="..\wsk\ns-wsk-_wsk_buf.md">WSK_BUF</a> structure as soon as the connect request is complete.

Before calling <b>WskConnectEx</b> with a provided send buffer, if the WSK application sets the <b>TCP_FASTOPEN</b> option on a WSK socket via the <a href="..\wsk\nc-wsk-pfn_wsk_control_socket.md">WskControlSocket</a> function the system will optionally send some or all of the data in a SYN packet. For more information, see the <b>TCP Fastopen</b> option in <a href="https://msdn.microsoft.com/2a10498d-0a0b-4a2d-941e-9aa45a1a4428">IPPROTO_TCP Socket Options</a>.




## -see-also

<a href="..\wsk\nc-wsk-pfn_wsk_bind.md">WskBind</a>



<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570822">SOCKADDR</a>



<a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a>



<a href="..\wsk\nc-wsk-pfn_wsk_disconnect_event.md">WskDisconnectEvent</a>



<a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a>



<a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a>



<a href="..\wsk\nc-wsk-pfn_wsk_disconnect.md">WskDisconnect</a>



<a href="..\wsk\nc-wsk-pfn_wsk_control_socket.md">WskControlSocket</a>



<a href="..\wsk\ns-wsk-_wsk_provider_stream_dispatch.md">
   WSK_PROVIDER_STREAM_DISPATCH</a>



<a href="..\wsk\ns-wsk-_wsk_provider_connection_dispatch.md">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_CONNECT_EX callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

