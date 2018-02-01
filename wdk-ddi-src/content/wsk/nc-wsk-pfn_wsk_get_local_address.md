---
UID: NC:wsk.PFN_WSK_GET_LOCAL_ADDRESS
title: PFN_WSK_GET_LOCAL_ADDRESS
author: windows-driver-content
description: The WskGetLocalAddress function retrieves the local transport address of a socket.
old-location: netvista\wskgetlocaladdress.htm
old-project: netvista
ms.assetid: 13cd4199-63f8-49f3-a12f-86e1d367b4aa
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.wskgetlocaladdress, WskGetLocalAddress callback function [Network Drivers Starting with Windows Vista], WskGetLocalAddress, PFN_WSK_GET_LOCAL_ADDRESS, PFN_WSK_GET_LOCAL_ADDRESS, wsk/WskGetLocalAddress, wskref_35a0f32f-247a-435c-83fe-0ba642f8519c.xml
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
-	WskGetLocalAddress
product: Windows
targetos: Windows
req.typenames: WNODE_HEADER, *PWNODE_HEADER
req.product: Windows 10 or later.
---

# PFN_WSK_GET_LOCAL_ADDRESS callback


## -description


The 
  <b>WskGetLocalAddress</b> function retrieves the local transport address of a socket.


## -prototype


````
PFN_WSK_GET_LOCAL_ADDRESS WskGetLocalAddress;

NTSTATUS WSKAPI * WskGetLocalAddress(
  _In_    PWSK_SOCKET Socket,
  _Out_   PSOCKADDR   LocalAddress,
  _Inout_ PIRP        Irp
)
{ ... }
````


## -parameters




### -param Socket [in]

A pointer to a 
     <a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a> structure that specifies the socket
     object for the socket that is being queried.


### -param LocalAddress [out]

A pointer to a caller-allocated buffer that receives the local transport address for the socket.
     The buffer must be located in non-paged memory. The buffer must also be large enough to contain the
     specific SOCKADDR structure type that corresponds to the address family that the WSK application
     specified when it created the socket.
     

For a connection-oriented socket that the WSK application accepted on a listening socket, the address
     family is the same as the address family that the WSK application specified when it created the
     listening socket.


### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the retrieve operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
     Kernel Functions</a>.


## -returns


<b>WskGetLocalAddress</b> returns one of the following NTSTATUS codes:
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
The local transport address for the socket was successfully retrieved. The IRP will be completed
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
The WSK subsystem could not retrieve the local transport address for the socket immediately. The
       WSK subsystem will complete the IRP after it has retrieved the local transport address for the socket.
       The status of the retrieve operation will be returned in the 
       <b>IoStatus.Status</b> field of the IRP.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
</td>
<td width="60%">
The socket is not bound to a local transport address. The IRP will be completed with failure
       status.

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
    <b>WskGetLocalAddress</b> function only on a socket that has been bound to a local transport address.

A listening, datagram, or stream socket is bound to a local transport address when the WSK application
    calls the 
    <a href="..\wsk\nc-wsk-pfn_wsk_bind.md">WskBind</a> function.

A connection-oriented socket is bound to a local transport address in one of the following ways:
<ul>
<li>
The WSK application calls the 
      <b>WskBind</b> function.

</li>
<li>
The WSK application creates, binds, and connects the socket by calling the 
      <a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a> function.

</li>
<li>
The WSK subsystem binds the socket when the WSK application accepts an incoming connection request
      on a listening socket.

</li>
</ul>The 
    <b>WskGetLocalAddress</b> function is particularly useful for determining the specific local transport
    address that was assigned to a socket by the transport protocol when the socket was bound to the local
    wildcard address. For a connection-oriented socket that was bound to the local wildcard address, the
    local transport address might not be assigned to the socket by the transport protocol until the socket is
    connected to a remote transport address. The step where the local transport address is assigned to the
    socket is transport protocol-dependent. For TCP, the port number is assigned when a connection-oriented
    socket is bound, but the IP address is not assigned until the socket is connected.

If the 
    <b>WskGetLocalAddress</b> function returns STATUS_PENDING, the buffer that is pointed to by the 
    <i>LocalAddress</i> parameter must remain valid until the IRP is completed. If the WSK application
    allocated the buffer with one of the 
    <b>ExAllocate<i>Xxx</i></b> functions, it cannot free the memory with the corresponding 
    <b>ExFree<i>Xxx</i></b> function until after the IRP is completed. If the WSK application allocated the buffer on the
    stack, it cannot return from the function that calls the 
    <b>WskGetLocalAddress</b> function until after the IRP is completed.



## -see-also

<a href="..\wsk\ns-wsk-_wsk_provider_datagram_dispatch.md">
   WSK_PROVIDER_DATAGRAM_DISPATCH</a>

<a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a>

<a href="..\wsk\nc-wsk-pfn_wsk_connect.md">WskConnect</a>

<a href="..\wsk\nc-wsk-pfn_wsk_accept_event.md">WskAcceptEvent</a>

<a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a>

<a href="..\wsk\ns-wsk-_wsk_provider_listen_dispatch.md">WSK_PROVIDER_LISTEN_DISPATCH</a>

<a href="..\wsk\nc-wsk-pfn_wsk_accept.md">WskAccept</a>

<a href="..\wsk\nc-wsk-pfn_wsk_bind.md">WskBind</a>

<a href="..\wsk\nc-wsk-pfn_wsk_get_remote_address.md">WskGetRemoteAddress</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570822">SOCKADDR</a>

<a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a>

<a href="..\wsk\ns-wsk-_wsk_provider_stream_dispatch.md">WSK_PROVIDER_STREAM_DISPATCH</a>

<a href="..\wsk\ns-wsk-_wsk_provider_connection_dispatch.md">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_GET_LOCAL_ADDRESS callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

