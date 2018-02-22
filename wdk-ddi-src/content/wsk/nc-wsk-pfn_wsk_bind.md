---
UID: NC:wsk.PFN_WSK_BIND
title: PFN_WSK_BIND
author: windows-driver-content
description: The WskBind function binds a socket to a local transport address.
old-location: netvista\wskbind.htm
old-project: netvista
ms.assetid: 520b02d0-a078-4af9-93a3-4fee5bbfee99
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.wskbind, WskBind callback function [Network Drivers Starting with Windows Vista], WskBind, PFN_WSK_BIND, PFN_WSK_BIND, wsk/WskBind, wskref_5d411257-ce57-4331-913a-c195e71a1138.xml
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
-	WskBind
product: Windows
targetos: Windows
req.typenames: "*PWPP_TRIAGE_INFO, WPP_TRIAGE_INFO"
req.product: Windows 10 or later.
---

# PFN_WSK_BIND callback


## -description


The 
  <b>WskBind</b> function binds a socket to a local transport address.


## -prototype


````
PFN_WSK_BIND WskBind;

NTSTATUS WSKAPI * WskBind(
  _In_       PWSK_SOCKET Socket,
  _In_       PSOCKADDR   LocalAddress,
  _Reserved_ ULONG       Flags,
  _Inout_    PIRP        Irp
)
{ ... }
````


## -parameters




### -param Socket [in]

A pointer to a 
     <a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a> structure that specifies the socket
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
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
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
    <a href="..\wsk\nc-wsk-pfn_wsk_connect.md">WskConnect</a> function. If a WSK application
    specifies a local wildcard address, the network stack binds the socket to the appropriate local transport
    address when the application calls 
    <b>WskConnect</b> to connect the socket to a remote transport address. In such a situation, the local
    transport address is determined by the system's routing information.

For a stream socket, calling the <b>WskBind</b> function binds the socket to the specified local transport address. If a WSK application specifies a local wildcard address, the network stack binds the socket to an available local transport address. <b>WskBind</b> must be called prior to calling the <a href="..\wsk\nc-wsk-pfn_wsk_listen.md">WskListen</a> or the <a href="..\wsk\nc-wsk-pfn_wsk_connect.md">WskConnect</a> functions.




## -see-also

<a href="..\wsk\ns-wsk-_wsk_provider_connection_dispatch.md">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>



<a href="..\wsk\ns-wsk-_wsk_provider_stream_dispatch.md">WSK_PROVIDER_STREAM_DISPATCH</a>



<a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570822">SOCKADDR</a>



<a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a>



<a href="..\wsk\ns-wsk-_wsk_provider_datagram_dispatch.md">
   WSK_PROVIDER_DATAGRAM_DISPATCH</a>



<a href="..\wsk\nc-wsk-pfn_wsk_connect.md">WskConnect</a>



<a href="..\wsk\ns-wsk-_wsk_provider_listen_dispatch.md">WSK_PROVIDER_LISTEN_DISPATCH</a>



<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_BIND callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

