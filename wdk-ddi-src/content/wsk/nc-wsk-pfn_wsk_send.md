---
UID: NC:wsk.PFN_WSK_SEND
title: PFN_WSK_SEND
author: windows-driver-content
description: The WskSend function sends data over a connection-oriented or stream socket to a remote transport address.
old-location: netvista\wsksend.htm
tech.root: netvista
ms.assetid: 40fe1e3b-22b2-4d78-a306-977188246935
ms.date: 05/02/2018
ms.keywords: PFN_WSK_SEND, PFN_WSK_SEND callback, WskSend, WskSend callback function [Network Drivers Starting with Windows Vista], netvista.wsksend, wsk/WskSend, wskref_978af27f-fa9e-4c21-9940-1d47b3fcb997.xml
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
-	WskSend
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_WSK_SEND callback function


## -description


The 
  <b>WskSend</b> function sends data over a connection-oriented or stream socket to a remote transport address.


## -parameters




### -param Socket [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a> structure that specifies the socket
     object for the socket over which to send the data.


### -param Buffer [in]

A pointer to an initialized 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571153">WSK_BUF</a> structure that describes the data buffer
     that contains the data that is being sent over the socket.


### -param Flags [in]

A ULONG value that contains a bitwise OR of a combination of the following flags:
     





#### WSK_FLAG_NODELAY

Directs the underlying transport to immediately send the data, and any previously queued data,
       to the remote application without delay.
       

This flag is supported by the Microsoft TCP/IP transport protocol. This flag might not be supported
       by other transport protocols.


### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the send operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
     Kernel Functions</a>.


## -returns



<b>WskSend</b> returns one of the following NTSTATUS codes:

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
Data was successfully sent over the socket. The IRP will be completed with success status. The 
       <b>IoStatus.Information</b> field of the IRP contains the number of bytes that were sent.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The WSK subsystem could not send the data over the socket immediately. The WSK subsystem will
       complete the IRP after it has sent the data over the socket. The status of the send operation will be
       returned in the 
       <b>IoStatus.Status</b> field of the IRP. If the operation succeeds, the 
       <b>IoStatus.Information</b> field of the IRP will contain the number of bytes that were sent.

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
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
A specified flag is not supported by the underlying network transport.

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
    <b>WskSend</b> function only on a connection-oriented or stream socket that has been previously connected to a
    remote transport address. A connection-oriented socket is connected to a remote transport address by one
    of the following methods:

<ul>
<li>
The WSK application connects the socket by calling the 
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
    <b>WskSend</b> function returns STATUS_PENDING, the MDL chain that is described in the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571153">WSK_BUF</a> structure that is pointed to by the 
    <i>Buffer</i> parameter must remain locked in memory until the IRP is completed.

The WSK subsystem does not perform any buffering of data when it sends data over a socket. Therefore,
    a call to the 
    <b>WskSend</b> function will not be completed by the WSK subsystem until all of the data has actually been
    sent.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571153">WSK_BUF</a>



<a href="https://msdn.microsoft.com/70a86809-07f2-4723-9e50-4dbdd31ff900">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>



<a href="https://msdn.microsoft.com/A10B901E-9987-40E9-976B-4CD9455E0AEE">WSK_PROVIDER_STREAM_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571124">WskCloseSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571139">WskReceive</a>



<a href="https://msdn.microsoft.com/2a7a7570-ed26-48be-b27b-dc240588ecfc">WskReceiveEvent</a>
 

 

