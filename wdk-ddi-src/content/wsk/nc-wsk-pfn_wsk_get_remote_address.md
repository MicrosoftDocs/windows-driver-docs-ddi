---
UID: NC:wsk.PFN_WSK_GET_REMOTE_ADDRESS
title: PFN_WSK_GET_REMOTE_ADDRESS
author: windows-driver-content
description: The WskGetRemoteAddress function retrieves the remote transport address of a connection-oriented or stream socket.
old-location: netvista\wskgetremoteaddress.htm
tech.root: netvista
ms.assetid: a2d65d55-744b-4851-b1fa-7087e0f06452
ms.date: 05/02/2018
ms.keywords: PFN_WSK_GET_REMOTE_ADDRESS, PFN_WSK_GET_REMOTE_ADDRESS callback, WskGetRemoteAddress, WskGetRemoteAddress callback function [Network Drivers Starting with Windows Vista], netvista.wskgetremoteaddress, wsk/WskGetRemoteAddress, wskref_5d771d25-f0bc-4292-a3cc-96704c0a39f3.xml
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
-	WskGetRemoteAddress
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_WSK_GET_REMOTE_ADDRESS callback function


## -description


The 
  <b>WskGetRemoteAddress</b> function retrieves the remote transport address of a connection-oriented
  or stream socket.


## -parameters




### -param Socket [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a> structure that specifies the socket
     object for the socket that is being queried.


### -param RemoteAddress [out]

A pointer to a caller-allocated buffer that receives the remote transport address for the socket.
     The buffer must be located in non-paged memory. The buffer must also be large enough to contain the
     specific SOCKADDR structure type that corresponds to the address family that the WSK application
     specified when it created the socket.
     

For a connection-oriented socket that the WSK application accepted on a listening socket, the address
     family is the same as the address family that the WSK application specified when it created the
     listening socket.


### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the retrieve operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
     Kernel Functions</a>.


## -returns



<b>WskGetRemoteAddress</b> returns one of the following NTSTATUS codes:

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
The remote transport address for the socket was successfully retrieved. The IRP will be
       completed with success status.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The WSK subsystem could not retrieve the remote transport address for the socket immediately.
       The WSK subsystem will complete the IRP after it has retrieved the remote transport address for the
       socket. The status of the retrieve operation will be returned in the 
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
The socket is not connected to a remote transport address. The IRP will be completed with
       failure status.

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
    <b>WskGetRemoteAddress</b> function only on a connection-oriented or stream socket that has been connected to a
    remote transport address. A stream socket is connected to a remote transport address by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff571125">WskConnect</a> function. A connection-oriented socket is connected to a remote transport address in one
    of the following ways:

<ul>
<li>
The WSK application calls the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff571125">WskConnect</a> function.

</li>
<li>
The WSK application creates, binds, and connects the socket by calling the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff571150">WskSocketConnect</a> function.

</li>
<li>
The WSK subsystem connects the socket when the WSK application accepts an incoming connection
      request on a listening socket.

</li>
</ul>
If the 
    <b>WskGetRemoteAddress</b> function returns STATUS_PENDING, the buffer that is pointed to by the 
    <i>RemoteAddress</i> parameter must remain valid until the IRP is completed. If the WSK application
    allocated the buffer with one of the 
    <b>ExAllocate<i>Xxx</i></b> functions, it cannot free the memory with the corresponding 
    <b>ExFree<i>Xxx</i></b> function until after the IRP is completed. If the WSK application allocated the buffer on the
    stack, it cannot return from the function that calls the 
    <b>WskGetRemoteAddress</b> function until after the IRP is completed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570822">SOCKADDR</a>



<a href="https://msdn.microsoft.com/70a86809-07f2-4723-9e50-4dbdd31ff900">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>



<a href="https://msdn.microsoft.com/A10B901E-9987-40E9-976B-4CD9455E0AEE">WSK_PROVIDER_STREAM_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571109">WskAccept</a>



<a href="https://msdn.microsoft.com/672440f0-810a-4e68-82a5-d038770898c5">WskAcceptEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571121">WskBind</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571124">WskCloseSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571125">WskConnect</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571133">WskGetLocalAddress</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571150">WskSocketConnect</a>
 

 

