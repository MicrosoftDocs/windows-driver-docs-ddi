---
UID: NC:wsk.PFN_WSK_CLOSE_SOCKET
title: PFN_WSK_CLOSE_SOCKET
author: windows-driver-content
description: The WskCloseSocket function closes a socket and frees any associated resources.
old-location: netvista\wskclosesocket.htm
tech.root: netvista
ms.assetid: 4d4e4a40-db76-4746-8049-3af8c4541283
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: PFN_WSK_CLOSE_SOCKET, PFN_WSK_CLOSE_SOCKET callback, WskCloseSocket, WskCloseSocket callback function [Network Drivers Starting with Windows Vista], netvista.wskclosesocket, wsk/WskCloseSocket, wskref_c8c37dfe-294f-4a40-9b3a-f4ca609ad4d8.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wsk.h
api_name:
-	WskCloseSocket
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_WSK_CLOSE_SOCKET callback function


## -description


The 
  <b>WskCloseSocket</b> function closes a socket and frees any associated resources.


## -parameters




### -param Socket [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a> structure that specifies the socket
     object for the socket that is being closed.


### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the close operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a>, 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571150">WskSocketConnect</a>, or 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571127">WskControlSocket</a> is not released when the
    socket is closed. A WSK application must release the cached copy of the security descriptor by using the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571180">WSK_RELEASE_SD</a> client control operation when
    the security descriptor is no longer needed.

The WSK subsystem deallocates the memory for the socket's socket object, 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a>, which was allocated by the WSK
    subsystem when the socket was created.

For connection-oriented sockets, the 
    <b>WskCloseSocket</b> function always performs an abortive disconnect of the socket unless the socket is
    already fully disconnected in both directions. To gracefully disconnect a connection-oriented socket from
    a remote transport address, a WSK application should call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571129">WskDisconnect</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571171">WSK_PROVIDER_BASIC_DISPATCH</a>



<a href="https://msdn.microsoft.com/70a86809-07f2-4723-9e50-4dbdd31ff900">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>



<a href="https://msdn.microsoft.com/fa8d3395-b800-4e5c-af03-b21520f69158">
   WSK_PROVIDER_DATAGRAM_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571176">WSK_PROVIDER_LISTEN_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571127">WskControlSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571129">WskDisconnect</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571150">WskSocketConnect</a>
 

 

