---
UID: NS:wsk._WSK_SOCKET
title: "_WSK_SOCKET"
author: windows-driver-content
description: The WSK_SOCKET structure defines a socket object for a socket.
old-location: netvista\wsk_socket.htm
old-project: netvista
ms.assetid: dce4a087-a14b-400b-bdc1-944c1d4d492a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWSK_SOCKET, PWSK_SOCKET, PWSK_SOCKET structure pointer [Network Drivers Starting with Windows Vista], WSK_SOCKET, WSK_SOCKET structure [Network Drivers Starting with Windows Vista], _WSK_SOCKET, netvista.wsk_socket, wsk/PWSK_SOCKET, wsk/WSK_SOCKET, wskref_bc4b638d-4210-486a-83b8-4483481b5d27.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wsk.h
api_name:
-	WSK_SOCKET
product: Windows
targetos: Windows
req.typenames: WSK_SOCKET, *PWSK_SOCKET
req.product: Windows 10 or later.
---

# _WSK_SOCKET structure


## -description


The WSK_SOCKET structure defines a socket object for a socket.


## -syntax


````
typedef struct _WSK_SOCKET {
  const VOID *Dispatch;
} WSK_SOCKET, *PWSK_SOCKET;
````


## -struct-fields




### -field Dispatch

A pointer to a constant provider dispatch structure. This structure is a dispatch table that
     contains pointers to a socket's functions. Depending on the WSK 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/winsock-kernel-socket-categories">socket category</a> of the
     socket, this pointer is a pointer to one of the following structures:
     

<table>
<tr>
<th>Socket category</th>
<th>Dispatch table structure</th>
</tr>
<tr>
<td>
Basic socket

</td>
<td>

<a href="..\wsk\ns-wsk-_wsk_provider_basic_dispatch.md">
         WSK_PROVIDER_BASIC_DISPATCH</a>


</td>
</tr>
<tr>
<td>
Listening socket

</td>
<td>

<a href="..\wsk\ns-wsk-_wsk_provider_listen_dispatch.md">
         WSK_PROVIDER_LISTEN_DISPATCH</a>


</td>
</tr>
<tr>
<td>
Datagram socket

</td>
<td>

<a href="..\wsk\ns-wsk-_wsk_provider_datagram_dispatch.md">
         WSK_PROVIDER_DATAGRAM_DISPATCH</a>


</td>
</tr>
<tr>
<td>
Connection-oriented socket

</td>
<td>

<a href="..\wsk\ns-wsk-_wsk_provider_connection_dispatch.md">
         WSK_PROVIDER_CONNECTION_DISPATCH</a>


</td>
</tr>
<tr>
<td>
Stream socket

</td>
<td>

<a href="..\wsk\ns-wsk-_wsk_provider_stream_dispatch.md">
         WSK_PROVIDER_STREAM_DISPATCH</a>


</td>
</tr>
</table>
 


## -remarks



The WSK subsystem allocates and fills in a WSK_SOCKET structure whenever a new socket is created. A
    WSK application receives a pointer to the WSK_SOCKET structure for a socket from the WSK subsystem in one
    of the following ways:

<ul>
<li>
The WSK application calls the 
      <a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a> function to create a socket.

</li>
<li>
The WSK application calls the 
      <a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a> function to create,
      bind, and connect a connection-oriented socket.

</li>
<li>
The WSK application calls the 
      <a href="..\wsk\nc-wsk-pfn_wsk_accept.md">WskAccept</a> function to accept an incoming
      connection-oriented socket on a listening socket.

</li>
<li>
The WSK subsystem calls the WSK application's 
      <a href="..\wsk\nc-wsk-pfn_wsk_accept_event.md">WskAcceptEvent</a> event callback function to
      notify the WSK application that an incoming connection-oriented socket has been accepted on a listening
      socket.

</li>
</ul>
A WSK application passes the pointer to a socket's WSK_SOCKET structure when calling any of the
    socket's functions.

The WSK subsystem frees the memory for the WSK_SOCKET structure when the WSK application calls the 
    <a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a> function to close the
    socket.




## -see-also

<a href="..\wsk\ns-wsk-_wsk_provider_datagram_dispatch.md">
   WSK_PROVIDER_DATAGRAM_DISPATCH</a>



<a href="..\wsk\nc-wsk-pfn_wsk_accept.md">WskAccept</a>



<a href="..\wsk\ns-wsk-_wsk_provider_connection_dispatch.md">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>



<a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a>



<a href="..\wsk\ns-wsk-_wsk_provider_basic_dispatch.md">WSK_PROVIDER_BASIC_DISPATCH</a>



<a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a>



<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>



<a href="..\wsk\ns-wsk-_wsk_provider_stream_dispatch.md">WSK_PROVIDER_STREAM_DISPATCH</a>



<a href="..\wsk\ns-wsk-_wsk_provider_listen_dispatch.md">WSK_PROVIDER_LISTEN_DISPATCH</a>



<a href="..\wsk\nc-wsk-pfn_wsk_accept_event.md">WskAcceptEvent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_SOCKET structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

