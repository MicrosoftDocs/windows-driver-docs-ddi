---
UID: NC:wsk.PFN_WSK_CONNECT
title: PFN_WSK_CONNECT
author: windows-driver-content
description: The WskConnect function connects a connection-oriented or stream socket to a remote transport address.
old-location: netvista\wskconnect.htm
old-project: netvista
ms.assetid: 66942ba4-40f9-4fdc-97f3-859309cd870d
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.wskconnect, WskConnect callback function [Network Drivers Starting with Windows Vista], WskConnect, PFN_WSK_CONNECT, PFN_WSK_CONNECT, wsk/WskConnect, wskref_16a15402-b34a-40b7-87a7-881d422e0d1c.xml
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
-	WskConnect
product: Windows
targetos: Windows
req.typenames: "*PWNODE_HEADER, WNODE_HEADER"
req.product: Windows 10 or later.
---

# PFN_WSK_CONNECT callback


## -description


The 
  <b>WskConnect</b> function connects a connection-oriented or stream socket to a remote transport address.


## -prototype


````
PFN_WSK_CONNECT WskConnect;

NTSTATUS WSKAPI * WskConnect(
  _In_       PWSK_SOCKET Socket,
  _In_       PSOCKADDR   RemoteAddress,
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
     socket. This pointer must be a pointer to the specific SOCKADDR structure type that corresponds to the
     address family that the WSK application specified when it created the socket.


### -param Flags

This parameter is reserved for system use. A WSK application must set this parameter to
     zero.


### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the connect operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
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
       <a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a> function to close the
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
    <a href="..\wsk\nc-wsk-pfn_wsk_bind.md">WskBind</a> function.

For stream sockets, once <b>WskConnect</b> is successfully called on a stream socket, the socket is committed to a connection-oriented flow and may no longer call listening socket functions.

A WSK application can create, bind, and connect a connection-oriented socket in a single function call
    by calling the 
    <a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a> function rather than
    calling the 
    <a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a> function, the 
    <a href="..\wsk\nc-wsk-pfn_wsk_bind.md">WskBind</a> function, and then the 
    <b>WskConnect</b> function. We recommend calling the 
    <b>WskSocketConnect</b> function unless the WSK application needs to set a socket option or issue an I/O
    control operation before binding or connecting the socket.




## -see-also

<a href="..\wsk\ns-wsk-_wsk_provider_connection_dispatch.md">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>



<a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a>



<a href="..\wsk\nc-wsk-pfn_wsk_disconnect_event.md">WskDisconnectEvent</a>



<a href="..\wsk\nc-wsk-pfn_wsk_bind.md">WskBind</a>



<a href="..\wsk\nc-wsk-pfn_wsk_disconnect.md">WskDisconnect</a>



<a href="..\wsk\ns-wsk-_wsk_provider_stream_dispatch.md">
   WSK_PROVIDER_STREAM_DISPATCH</a>



<a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a>



<a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a>



<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570822">SOCKADDR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_CONNECT callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

