---
UID: NC:wsk.PFN_WSK_RECEIVE_FROM
title: PFN_WSK_RECEIVE_FROM
author: windows-driver-content
description: The WskReceiveFrom function receives a datagram and any associated control information from a remote transport address.
old-location: netvista\wskreceivefrom.htm
tech.root: netvista
ms.assetid: 769fea0d-e35a-4385-8027-f1518c25b637
ms.date: 05/02/2018
ms.keywords: PFN_WSK_RECEIVE_FROM, PFN_WSK_RECEIVE_FROM callback, WskReceiveFrom, WskReceiveFrom callback function [Network Drivers Starting with Windows Vista], netvista.wskreceivefrom, wsk/WskReceiveFrom, wskref_5c6ab859-3010-468f-8cb2-820cbb641a19.xml
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
-	WskReceiveFrom
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_WSK_RECEIVE_FROM callback function


## -description


The 
  <b>WskReceiveFrom</b> function receives a datagram and any associated control information from a remote
  transport address.


## -parameters




### -param Socket [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a> structure that specifies the socket
     object for the datagram socket from which to receive the datagram.


### -param Buffer [in]

A pointer to an initialized 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571153">WSK_BUF</a> structure that describes the data buffer
     that receives the datagram from the socket.


### -param Flags

This parameter is reserved for system use. A WSK application must set this parameter to
     zero.


### -param RemoteAddress [out, optional]

A pointer to a caller-allocated buffer that receives the remote transport address from which the
     received datagram originated. The buffer must be located in non-paged memory. The buffer must also be
     large enough to contain the specific SOCKADDR structure type that corresponds to the address family that
     the WSK application specified when it created the datagram socket. This pointer is optional and can be
     <b>NULL</b>.


### -param ControlLength


### -param ControlInfo [out, optional]

A pointer to a caller-allocated buffer that receives the control information that is associated
     with the received datagram. The control information data that is associated with a datagram is made up
     of one or more control data objects, each of which begins with a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544964">CMSGHDR</a> structure. If there is no control
     information present for the received datagram, the contents of the buffer are undefined. This pointer is
     optional and can be <b>NULL</b>. If the 
     <i>ControlInfoLength</i> parameter is <b>NULL</b>, the 
     <i>ControlInfo</i> parameter should be <b>NULL</b>.


### -param ControlFlags [out, optional]

A pointer to a ULONG-typed variable that receives the bitwise OR of a combination of the following
     flags:
     





#### MSG_BCAST

The datagram was received as a link-layer broadcast or with a destination transport address that
       is a broadcast address.



#### MSG_MCAST

The datagram was received with a destination transport address that is a multicast
       address.



#### MSG_TRUNC

The datagram was truncated because the size of the datagram was larger than the size of the
       buffer that is specified by the 
       <i>Buffer</i> parameter.



#### MSG_CTRUNC

The control information data was truncated because the number of bytes of control information
       was greater than the size of the buffer that is specified by the 
       <i>ControlInfo</i> parameter.

This parameter is optional and can be <b>NULL</b>.


### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the receive operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
     Kernel Functions</a>.


#### - ControlInfoLength [in, out]

A pointer to a ULONG-typed variable that specifies the size of the buffer that is pointed to by
     the 
     <i>ControlInfo</i> parameter. When the receive operation is complete, the variable receives the size of
     the control information that is associated with the received datagram. If the value that is returned is
     zero, there is no control information present for the datagram. This pointer is optional and can be
     <b>NULL</b>. If this parameter is <b>NULL</b>, the 
     <i>ControlInfo</i> parameter is ignored.


## -returns



<b>WskReceiveFrom</b> returns one of the following NTSTATUS codes:

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
Data was successfully received from the socket. The IRP will be completed with success status.
       The 
       <b>IoStatus.Information</b> field of the IRP contains the number of bytes that were received.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The WSK subsystem could not receive the datagram from the socket immediately. The WSK subsystem
       will complete the IRP after it has received the datagram from the socket. The status of the receive
       operation will be returned in the 
       <b>IoStatus.Status</b> field of the IRP. If the operation succeeds, the 
       <b>IoStatus.Information</b> field of the IRP will contain the number of bytes that were
       received.

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



If the WSK application has set a fixed remote transport address for the datagram socket, datagrams
    that are received from any other remote transport address will be discarded by the WSK subsystem. For
    more information about setting the remote transport address for a datagram socket, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/sio-wsk-set-remote-address">SIO_WSK_SET_REMOTE_ADDRESS</a>.

If a WSK application's 
    <a href="https://msdn.microsoft.com/1cdb8a70-54fe-44a6-a16c-71cbf6a49ef2">WskReceiveFromEvent</a> event callback
    function is enabled on a datagram socket and the application also has a pending call to the 
    <b>WskReceiveFrom</b> function on the same datagram socket, then, when datagrams arrive, the pending call
    to the 
    <b>WskReceiveFrom</b> function will take precedence over the 
    <i>WskReceiveFromEvent</i> event callback function. The WSK subsystem calls the application's 
    <i>WskReceiveFromEvent</i> event callback function only if there are no IRPs queued from pending calls to
    the 
    <b>WskReceiveFrom</b> function. However, a WSK application should not assume that the WSK subsystem will
    not call the application's 
    <i>WskReceiveFromEvent</i> event callback function for a datagram socket that has a pending call to the 
    <b>WskReceiveFrom</b> function. Race conditions exist where the WSK subsystem could still call the WSK
    application's 
    <i>WskReceiveFromEvent</i> event callback function for the socket. The only way for a WSK application to
    ensure that the WSK subsystem will not call the application's 
    <i>WskReceiveFromEvent</i> event callback function on a datagram socket is to disable the application's 
    <i>WskReceiveFromEvent</i> event callback function on the socket.

If the 
    <b>WskReceiveFrom</b> function returns STATUS_PENDING, the MDL chain that is described in the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571153">WSK_BUF</a> structure that is pointed to by the 
    <i>Buffer</i> parameter must remain locked in memory until the IRP is completed. In addition, the variable
    that is pointed to by the 
    <i>ControlInfoLength</i> parameter, the buffer that is pointed to by the 
    <i>ControlInfo</i> parameter, and the variable that is pointed to by the 
    <i>ControlFlags</i> parameter must also remain valid until the IRP is completed. If the WSK application
    allocated these buffers or variables with one of the 
    <b>ExAllocate<i>Xxx</i></b> functions, it cannot free the memory with the corresponding 
    <b>ExFree<i>Xxx</i></b> function until after the IRP is completed. If the WSK application allocated these buffers or
    variables on the stack, it cannot return from the function that calls the 
    <b>WskReceiveFrom</b> function until after the IRP is completed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544964">CMSGHDR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/sio-wsk-set-remote-address">SIO_WSK_SET_REMOTE_ADDRESS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570822">SOCKADDR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571153">WSK_BUF</a>



<a href="https://msdn.microsoft.com/fa8d3395-b800-4e5c-af03-b21520f69158">
   WSK_PROVIDER_DATAGRAM_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571124">WskCloseSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571127">WskControlSocket</a>



<a href="https://msdn.microsoft.com/1cdb8a70-54fe-44a6-a16c-71cbf6a49ef2">WskReceiveFromEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571148">WskSendTo</a>
 

 

