---
UID: NC:wsk.PFN_WSK_ACCEPT
title: PFN_WSK_ACCEPT
author: windows-driver-content
description: The WskAccept function accepts an incoming connection on a listening socket.
old-location: netvista\wskaccept.htm
old-project: netvista
ms.assetid: 9fa8bb07-7ee5-400b-aaca-33db3911d79f
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: PFN_WSK_ACCEPT, WskAccept, WskAccept callback function [Network Drivers Starting with Windows Vista], netvista.wskaccept, wsk/WskAccept, wskref_22de82fc-18c4-4fed-b0fe-7e048ba7cfeb.xml
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
-	WskAccept
product: Windows
targetos: Windows
req.typenames: WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO
req.product: Windows 10 or later.
---

# PFN_WSK_ACCEPT callback


## -description


The 
  <b>WskAccept</b> function accepts an incoming connection on a listening socket.


## -parameters




### -param ListenSocket [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a> structure that specifies the socket
     object for the listening or stream socket that is being checked for an incoming connection.


### -param Flags

This parameter is reserved for system use. A WSK application must set this parameter to
     zero.


### -param AcceptSocketContext [in, optional]

A pointer to a caller-supplied context for the socket that is being accepted. The WSK subsystem
     passes this pointer to the accepted socket's event callback functions. The context information is opaque
     to the WSK subsystem. The context information must be stored in non-paged memory. If the WSK application
     will not be enabling any event callback functions on the accepted socket, it should set this pointer to
     <b>NULL</b>.


### -param *AcceptSocketDispatch [in, optional]

A pointer to a constant 
     <a href="https://msdn.microsoft.com/960eee8a-2950-4baf-b32d-be13b3d65951">
     WSK_CLIENT_CONNECTION_DISPATCH</a> structure. This structure is a dispatch table that contains
     pointers to the event callback functions for the accepted socket. If the WSK application will not be
     enabling all of the event callback functions for the accepted socket, it should set the pointers in the
     dispatch table to <b>NULL</b> for those event callback functions that it does not enable. If the WSK
     application will not be enabling any event callback functions on the accepted socket, it should set this
     pointer to <b>NULL</b>.


### -param LocalAddress [out, optional]

A pointer to a caller-allocated buffer that receives the local transport address on which the
     incoming connection arrived. The buffer must be located in non-paged memory. The buffer must also be
     large enough to contain the specific SOCKADDR structure type that corresponds to the address family that
     the WSK application specified when it created the listening socket. This pointer is optional and can be
     <b>NULL</b>.


### -param RemoteAddress [out, optional]

A pointer to a caller-allocated buffer that receives the remote transport address from which the
     incoming connection originated. The buffer must be located in non-paged memory. The buffer must also be
     large enough to contain the specific SOCKADDR structure type that corresponds to the address family that
     the WSK application specified when it created the listening socket. This pointer is optional and can be
     <b>NULL</b>.


### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the accept operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
     Kernel Functions</a>.


## -returns



<b>WskAccept</b> returns one of the following NTSTATUS codes:

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
An incoming connection was successfully accepted. The IRP will be completed with success
       status.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The IRP has been queued by the WSK subsystem, which is waiting for an incoming connection on the
       listening socket.

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
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff571124">WskCloseSocket</a> function to close the
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
    <b>WskAccept</b> function on either a listening socket or stream socket that it previously bound to a local transport address
    by calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571121">WskBind</a> function.

The behavior of the 
    <b>WskAccept</b> function depends on whether an incoming connection is waiting to be accepted on the
    listening socket:

<ul>
<li>
If an incoming connection has already arrived on the listening socket and is waiting to be accepted,
      the 
      <b>WskAccept</b> function returns STATUS_SUCCESS. In this situation, the IRP is completed with success
      status and the 
      <b>IoStatus.Information</b> field of the IRP contains a pointer to the socket object for the accepted
      socket.

</li>
<li>
If an incoming connection is not waiting to be accepted on the listening socket, 
      <b>WskAccept</b> returns STATUS_PENDING and the WSK subsystem queues the IRP until an incoming
      connection is received. When an incoming connection is received, the WSK subsystem asynchronously
      completes the IRP with success status. In this situation, the 
      <b>IoStatus.Information</b> field of the IRP contains a pointer to the socket object for the accepted
      socket.

</li>
</ul>
If a WSK application's 
    <a href="https://msdn.microsoft.com/672440f0-810a-4e68-82a5-d038770898c5">WskAcceptEvent</a> event callback function is
    enabled on a listening socket and the application has a pending call to the 
    <b>WskAccept</b> function on the same listening socket, then, when an incoming connection arrives, the
    pending call to 
    <b>WskAccept</b> takes precedence over the 
    <i>WskAcceptEvent</i> event callback function. The WSK subsystem calls the application's 
    <i>WskAcceptEvent</i> event callback function only if there are no IRPs queued from pending calls to 
    <b>WskAccept</b>. However, a WSK application should not assume that the WSK subsystem will not call the
    application's 
    <i>WskAcceptEvent</i> event callback function for a listening socket that has a pending call to the 
    <b>WskAccept</b> function. Race conditions exist where the WSK subsystem could still call the WSK
    application's 
    <i>WskAcceptEvent</i> event callback function for the socket. The only way for a WSK application to ensure
    that the WSK subsystem will not call the application's 
    <i>WskAcceptEvent</i> event callback function for a listening socket is to disable the application's 
    <i>WskAcceptEvent</i> event callback function on the socket.

When the 
    <b>WskAccept</b> function successfully accepts an incoming connection, all of the event callback functions
    on the accepted socket are disabled by default. For more information about enabling any of the accepted
    socket's event callback functions, see 
    <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa363707">Enabling and
    Disabling Event Callback Functions</a>.

If a WSK application specifies a non-<b>NULL</b> pointer in the 
    <i>LocalAddress</i> parameter, in the 
    <i>RemoteAddress</i> parameter, or in both parameters, and if 
    <b>WskAccept</b> returns STATUS_PENDING, the buffers that are pointed to by those parameters must remain
    valid until the IRP is completed. If the WSK application allocated the buffers with one of the 
    <b>ExAllocate<i>Xxx</i></b> functions, it cannot free the memory with the corresponding 
    <b>ExFree<i>Xxx</i></b> function until after the IRP is completed. If the WSK application allocated the buffers on the
    stack, it cannot return from the function that calls the 
    <b>WskAccept</b> function until after the IRP is completed.

The WSK subsystem allocates the memory for the socket object structure (
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a>) for the accepted connection on
    behalf of the WSK application. The WSK subsystem deallocates this memory when the socket is closed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570822">SOCKADDR</a>



<a href="https://msdn.microsoft.com/960eee8a-2950-4baf-b32d-be13b3d65951">
   WSK_CLIENT_CONNECTION_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571176">WSK_PROVIDER_LISTEN_DISPATCH</a>



<a href="https://msdn.microsoft.com/A10B901E-9987-40E9-976B-4CD9455E0AEE">WSK_PROVIDER_STREAM_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a>



<a href="https://msdn.microsoft.com/672440f0-810a-4e68-82a5-d038770898c5">WskAcceptEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571121">WskBind</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571124">WskCloseSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_ACCEPT callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
