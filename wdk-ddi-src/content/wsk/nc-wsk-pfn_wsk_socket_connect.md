---
UID: NC:wsk.PFN_WSK_SOCKET_CONNECT
title: PFN_WSK_SOCKET_CONNECT
author: windows-driver-content
description: The WskSocketConnect function creates a new connection-oriented socket, binds it to a local transport address, connects it to a given remote transport address, and returns a pointer to the associated socket object.
old-location: netvista\wsksocketconnect.htm
old-project: netvista
ms.assetid: b1482160-49db-4490-b347-ff9396abf2ff
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: PFN_WSK_SOCKET_CONNECT, WskSocketConnect, WskSocketConnect callback function [Network Drivers Starting with Windows Vista], netvista.wsksocketconnect, wsk/WskSocketConnect, wskref_326c63cb-233d-4b6e-9c36-15e7f2cb1f1c.xml
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
-	WskSocketConnect
product:
- Windows
targetos: Windows
req.typenames: WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO
req.product: Windows 10 or later.
---

# PFN_WSK_SOCKET_CONNECT callback


## -description


The 
  <b>WskSocketConnect</b> function creates a new connection-oriented socket, binds it to a local transport
  address, connects it to a given remote transport address, and returns a pointer to the associated socket
  object.


## -parameters




### -param Client [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571155">WSK_CLIENT</a> structure that was returned through
     the 
     <i>WskProviderNpi</i> parameter of the 
     <a href="https://msdn.microsoft.com/b5c6667e-33b4-4482-8817-c01d9d314c3a">
     WskCaptureProviderNPI</a> function.


### -param SocketType [in]

The type of the socket that is being created. The following socket types are supported:
     





#### SOCK_STREAM

Supports reliable connection-oriented byte stream communication.



#### SOCK_DGRAM

Supports unreliable connectionless datagram communication.



#### SOCK_RAW

Supports raw access to the transport protocol.

For more information about the socket types that are supported for each supported address family, see
     
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571151">WSK Address Families</a>.


### -param Protocol [in]

The transport protocol for the socket that is being created. For more information about the
     protocols that are supported for each supported address family, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571151">WSK Address Families</a>.


### -param LocalAddress [in]

A pointer to a structure that specifies the local transport address to which to bind the socket.
     The WSK application must specify a pointer to the specific SOCKADDR structure type that corresponds to
     the address family for the socket that is being created.


### -param RemoteAddress [in]

A pointer to a structure that specifies the remote transport address to which to connect the
     socket. The WSK application must specify a pointer to the specific SOCKADDR structure type that
     corresponds to the address family for the socket that is being created.


### -param Flags

This parameter is reserved for system use. WSK applications must set this parameter to
     zero.


### -param SocketContext [in, optional]

A pointer to a caller-supplied context for the socket that is being created. The WSK subsystem
     passes this pointer to the socket's event callback functions. The context information is opaque to the
     WSK subsystem and must be stored in non-paged memory. If the WSK application will not be enabling any
     event callback functions on the new socket, it should set this pointer to <b>NULL</b>.


### -param *Dispatch [in, optional]

A pointer to a constant 
     <a href="https://msdn.microsoft.com/960eee8a-2950-4baf-b32d-be13b3d65951">
     WSK_CLIENT_CONNECTION_DISPATCH</a> structure. This structure is a dispatch table that contains
     pointers to the event callback functions for the new socket. If the WSK application will not be enabling
     all of the event callback functions for the new socket, it should set the pointers in the dispatch table
     to <b>NULL</b> for those event callback functions that it does not enable. If the WSK application will not be
     enabling any event callback functions on the new socket, it should set this pointer to <b>NULL</b>.


### -param OwningProcess [in, optional]

A pointer to the process from which the WSK subsystem will retrieve the security context to use
     when it binds the socket. The WSK subsystem uses the security context to determine whether the local
     transport address can be shared if that address is already in use. To specify the current process, a WSK
     application sets this pointer to <b>NULL</b>.


### -param OwningThread [in, optional]

A pointer to a specific thread from which the WSK subsystem will retrieve the security context to
     use when it binds the socket. The WSK subsystem uses the security context to determine whether the local
     transport address can be shared if that address is already in use. If a WSK application does not need to
     specify a specific thread, it sets this pointer to <b>NULL</b>.


### -param SecurityDescriptor [in, optional]

A pointer to a SECURITY_DESCRIPTOR structure that specifies the security descriptor to apply to
     the socket that is being created. The security descriptor controls the sharing of the local transport
     address to which the socket is bound. If a WSK application specifies a non-<b>NULL</b> pointer, it must specify
     a pointer to a cached copy of a security descriptor that was obtained by calling the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571126">WskControlClient</a> function with the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571154">WSK_CACHE_SD</a> control code. To specify a
     default security descriptor that does not allow sharing of the local transport address, a WSK
     application sets 
     <i>SecurityDescriptor</i> to <b>NULL</b>.
     

For more information about the SECURITY_DESCRIPTOR structure, see the reference page for
     SECURITY_DESCRIPTOR in the Microsoft Windows SDK documentation.


### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the creation of the
     new socket asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
     Kernel Functions</a>.


## -returns



<b>WskSocketConnect</b> returns one of the following NTSTATUS codes:

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
The new socket was successfully created. The IRP will be completed with success status.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The WSK subsystem could not create the socket immediately. The WSK subsystem will complete the
       IRP after it has created the new socket. The status of the socket creation will be returned in the 
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



If the IRP is completed with success status, the 
    <b>IoStatus.Information</b> field of the IRP contains a pointer to a socket object structure (
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a>) for the new socket.

A WSK application can obtain a list of available transport protocols by calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571126">WskControlClient</a> function with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571195">WSK_TRANSPORT_LIST_QUERY</a> control
    code. 
    <b>WskControlClient</b> returns a list of 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571193">WSK_TRANSPORT</a> structures that contains all of
    the valid combinations of the 
    <i>SocketType</i> and 
    <i>Protocol</i> parameters.

The WSK subsystem determines the address family for the new socket from the address family that is
    specified in the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570822">SOCKADDR</a> structure that is pointed to by the 
    <i>LocalAddress</i> parameter.

If the WSK application needs to set a socket option or issue an I/O control operation on the socket
    before binding or connecting the socket, the WSK application must call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a>, 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571121">WskBind</a>, and 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571125">WskConnect</a> functions instead of calling the 
    <b>WskSocketConnect</b> function.

When a WSK application successfully creates a new socket, all of the event callback functions on the
    new socket are disabled by default. For more information about enabling any of the new socket's event
    callback functions, see 
    <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa363707">Enabling and
    Disabling Event Callback Functions</a>.

If a WSK application specifies a non-<b>NULL</b> pointer for the 
    <i>SecurityDescriptor</i> parameter, it must not release the cached security descriptor until after the
    IRP is completed.

The WSK subsystem allocates the memory for the socket object structure (WSK_SOCKET) for the new socket
    on behalf of the WSK application. The WSK subsystem deallocates this memory when the socket is
    closed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570822">SOCKADDR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571155">WSK_CLIENT</a>



<a href="https://msdn.microsoft.com/960eee8a-2950-4baf-b32d-be13b3d65951">
   WSK_CLIENT_CONNECTION_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571175">WSK_PROVIDER_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571177">WSK_PROVIDER_NPI</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571122">WskCaptureProviderNPI</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571124">WskCloseSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571126">WskControlClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a>
 

 

