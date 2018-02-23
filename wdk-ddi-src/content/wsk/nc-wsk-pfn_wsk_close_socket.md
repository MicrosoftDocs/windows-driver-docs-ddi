---
UID: NC:wsk.PFN_WSK_CLOSE_SOCKET
title: PFN_WSK_CLOSE_SOCKET
author: windows-driver-content
description: The WskCloseSocket function closes a socket and frees any associated resources.
old-location: netvista\wskclosesocket.htm
old-project: netvista
ms.assetid: 4d4e4a40-db76-4746-8049-3af8c4541283
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.wskclosesocket, WskCloseSocket callback function [Network Drivers Starting with Windows Vista], WskCloseSocket, PFN_WSK_CLOSE_SOCKET, PFN_WSK_CLOSE_SOCKET, wsk/WskCloseSocket, wskref_c8c37dfe-294f-4a40-9b3a-f4ca609ad4d8.xml
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
-	WskCloseSocket
product: Windows
targetos: Windows
req.typenames: "*PWPP_TRIAGE_INFO, WPP_TRIAGE_INFO"
req.product: Windows 10 or later.
---

# PFN_WSK_CLOSE_SOCKET callback


## -description


The 
  <b>WskCloseSocket</b> function closes a socket and frees any associated resources.


## -prototype


````
PFN_WSK_CLOSE_SOCKET WskCloseSocket;

NTSTATUS WSKAPI * WskCloseSocket(
  _In_    PWSK_SOCKET Socket,
  _Inout_ PIRP        Irp
)
{ ... }
````


## -parameters




### -param Socket [in]

A pointer to a 
     <a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a> structure that specifies the socket
     object for the socket that is being closed.


### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the close operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
     Kernel Functions</a>.


## -returns



<b>WskCloseSocket</b> returns one of the following NTSTATUS codes:

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
The socket was successfully closed. The IRP will be completed with success status.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The WSK subsystem could not close the socket immediately. The WSK subsystem will complete the
       IRP after it has closed the socket. The status of the close operation will be returned in the 
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



Before calling the 
    <b>WskCloseSocket</b> function, a WSK application must ensure that there are no other function calls in
    progress to any of the socket's functions, including any extension functions, in any of the application's
    other threads. For example, a WSK application must not call 
    <b>WskCloseSocket</b> on a socket in one thread while the application is calling 
    <b>WskSend</b> on the same socket in another thread. Any in-progress calls to the socket's functions must
    return control back to the WSK application before it calls 
    <b>WskCloseSocket</b> to close the socket. However, a WSK application can call 
    <b>WskCloseSocket</b> if there are pending IRPs from prior calls to the socket's functions that have not
    yet completed.

Calling the 
    <b>WskCloseSocket</b> function causes the WSK subsystem to cancel and complete all pending IRPs from prior
    calls to the socket's functions. The WSK subsystem also ensures that any in-progress event callback
    functions have returned control back to the WSK subsystem before it closes the socket.

After a WSK application has called 
    <b>WskCloseSocket</b>, it should not make any further calls to any of the socket's functions.

If a WSK application applies a security descriptor to a socket, the cached copy of the security
    descriptor that is specified in the call to 
    <a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>, 
    <a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a>, or 
    <a href="..\wsk\nc-wsk-pfn_wsk_control_socket.md">WskControlSocket</a> is not released when the
    socket is closed. A WSK application must release the cached copy of the security descriptor by using the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571180">WSK_RELEASE_SD</a> client control operation when
    the security descriptor is no longer needed.

The WSK subsystem deallocates the memory for the socket's socket object, 
    <a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a>, which was allocated by the WSK
    subsystem when the socket was created.

For connection-oriented sockets, the 
    <b>WskCloseSocket</b> function always performs an abortive disconnect of the socket unless the socket is
    already fully disconnected in both directions. To gracefully disconnect a connection-oriented socket from
    a remote transport address, a WSK application should call the 
    <a href="..\wsk\nc-wsk-pfn_wsk_disconnect.md">WskDisconnect</a> function.




## -see-also

<a href="..\wsk\ns-wsk-_wsk_provider_connection_dispatch.md">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>



<a href="..\wsk\nc-wsk-pfn_wsk_disconnect.md">WskDisconnect</a>



<a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a>



<a href="..\wsk\nc-wsk-pfn_wsk_control_socket.md">WskControlSocket</a>



<a href="..\wsk\ns-wsk-_wsk_provider_datagram_dispatch.md">
   WSK_PROVIDER_DATAGRAM_DISPATCH</a>



<a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a>



<a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a>



<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>



<a href="..\wsk\ns-wsk-_wsk_provider_basic_dispatch.md">WSK_PROVIDER_BASIC_DISPATCH</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_CLOSE_SOCKET callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

