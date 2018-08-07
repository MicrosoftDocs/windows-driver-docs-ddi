---
UID: NC:wsk.PFN_WSK_CONNECT_EX
title: PFN_WSK_CONNECT_EX
author: windows-driver-content
description: The WskConnectEx function connects a connection-oriented or stream socket to a remote transport address.WskConnectEx is similar to WskConnect except that it can also optionally send a buffer of data during or after connection synchronization.
old-location: netvista\wskconnectex.htm
tech.root: netvista
ms.assetid: 1BC518E9-747C-4406-8A2A-40A3BCB0A3AA
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: PFN_WSK_CONNECT_EX, PFN_WSK_CONNECT_EX callback, WskConnectEx, WskConnectEx callback function [Network Drivers Starting with Windows Vista], netvista.wskconnectex, wsk/WskConnectEx
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_WSK_CONNECT_EX callback function


## -description


The 
  <b>WskConnectEx</b> function connects a connection-oriented or stream socket to a remote transport address.

<b>WskConnectEx</b> is similar to <a href="https://msdn.microsoft.com/library/windows/hardware/ff571125">WskConnect</a>
  except that it can also optionally send a buffer of data during or after connection synchronization.


## -parameters




### -param Socket [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a> structure that specifies the socket
     object for the socket that is being connected to a remote transport address.


### -param RemoteAddress [in]

A pointer to a structure that specifies the remote transport address to which to connect the
     socket. This pointer must be a pointer to the specific <a href="https://msdn.microsoft.com/library/windows/hardware/ff570822">SOCKADDR</a> structure type that corresponds to the
     address family that the WSK application specified when it created the socket.


### -param Buffer [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff571153">WSK_BUF</a> structure, which contains the data to send during or after connection synchronization. The maximum allowed size in bytes is 65,535.


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
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff571124">WskCloseSocket</a> function to close the
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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571150">WskSocketConnect</a> function rather than
    calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a> function, the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571121">WskBind</a> function, and then the 
    <b>WskConnectEx</b> function. We recommend calling the 
    <b>WskSocketConnect</b> function unless the WSK application needs to set a socket option or issue an I/O
    control operation before binding or connecting the socket.

A WSK application can call the 
    <b>WskConnectEx</b> function only on a connection-oriented or stream socket that the application previously bound to a
    local transport address by calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571121">WskBind</a> function.

For stream sockets, once <b>WskConnectEx</b> is successfully called on a stream socket, the socket is committed to a connection-oriented flow and may no longer call listening socket functions.

If the <i>Buffer</i> parameter is used, the caller can free the MDL in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff571153">WSK_BUF</a> structure as soon as the connect request is complete.

Before calling <b>WskConnectEx</b> with a provided send buffer, if the WSK application sets the <b>TCP_FASTOPEN</b> option on a WSK socket via the <a href="https://msdn.microsoft.com/library/windows/hardware/ff571127">WskControlSocket</a> function the system will optionally send some or all of the data in a SYN packet. For more information, see the <b>TCP Fastopen</b> option in <a href="https://msdn.microsoft.com/2a10498d-0a0b-4a2d-941e-9aa45a1a4428">IPPROTO_TCP Socket Options</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570822">SOCKADDR</a>



<a href="https://msdn.microsoft.com/70a86809-07f2-4723-9e50-4dbdd31ff900">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>



<a href="https://msdn.microsoft.com/A10B901E-9987-40E9-976B-4CD9455E0AEE">
   WSK_PROVIDER_STREAM_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571121">WskBind</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571124">WskCloseSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571127">WskControlSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571129">WskDisconnect</a>



<a href="https://msdn.microsoft.com/bf12d7b3-080e-46d9-b276-76d42068e7c6">WskDisconnectEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571150">WskSocketConnect</a>
 

 

