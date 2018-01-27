---
UID: NC:wsk.PFN_WSK_RECEIVE_FROM
title: PFN_WSK_RECEIVE_FROM
author: windows-driver-content
description: The WskReceiveFrom function receives a datagram and any associated control information from a remote transport address.
old-location: netvista\wskreceivefrom.htm
old-project: netvista
ms.assetid: 769fea0d-e35a-4385-8027-f1518c25b637
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.wskreceivefrom, WskReceiveFrom callback function [Network Drivers Starting with Windows Vista], WskReceiveFrom, PFN_WSK_RECEIVE_FROM, PFN_WSK_RECEIVE_FROM, wsk/WskReceiveFrom, wskref_5c6ab859-3010-468f-8cb2-820cbb641a19.xml
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
req.irql: <= DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	wsk.h
apiname: 
-	WskReceiveFrom
product: Windows
targetos: Windows
req.typenames: WNODE_HEADER, *PWNODE_HEADER
req.product: Windows 10 or later.
---

# PFN_WSK_RECEIVE_FROM callback


## -description


The 
  <b>WskReceiveFrom</b> function receives a datagram and any associated control information from a remote
  transport address.


## -prototype


````
PFN_WSK_RECEIVE_FROM WskReceiveFrom;

NTSTATUS WSKAPI * WskReceiveFrom(
  _In_       PWSK_SOCKET Socket,
  _In_       PWSK_BUF    Buffer,
  _Reserved_ ULONG       Flags,
  _Out_opt_  PSOCKADDR   RemoteAddress,
  _Inout_    PULONG      ControlInfoLength,
  _Out_opt_  PCMSGHDR    ControlInfo,
  _Out_opt_  PULONG      ControlFlags,
  _Inout_    PIRP        Irp
)
{ ... }
````


## -parameters




### -param Socket [in]

A pointer to a 
     <a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a> structure that specifies the socket
     object for the datagram socket from which to receive the datagram.


### -param Buffer [in]

A pointer to an initialized 
     <a href="..\wsk\ns-wsk-_wsk_buf.md">WSK_BUF</a> structure that describes the data buffer
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
     



This parameter is optional and can be <b>NULL</b>.


### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the receive operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <mshelp:link keywords="netvista.using_irps_with_winsock_kernel_functions" tabindex="0">Using IRPs with Winsock
     Kernel Functions</mshelp:link>.


##### - ControlFlags.MSG_BCAST

The datagram was received as a link-layer broadcast or with a destination transport address that
       is a broadcast address.


##### - ControlFlags.MSG_CTRUNC

The control information data was truncated because the number of bytes of control information
       was greater than the size of the buffer that is specified by the 
       <i>ControlInfo</i> parameter.


##### - ControlFlags.MSG_MCAST

The datagram was received with a destination transport address that is a multicast
       address.


##### - ControlFlags.MSG_TRUNC

The datagram was truncated because the size of the datagram was larger than the size of the
       buffer that is specified by the 
       <i>Buffer</i> parameter.


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


If the WSK application has set a fixed remote transport address for the datagram socket, datagrams
    that are received from any other remote transport address will be discarded by the WSK subsystem. For
    more information about setting the remote transport address for a datagram socket, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/sio-wsk-set-remote-address">SIO_WSK_SET_REMOTE_ADDRESS</a>.

If a WSK application's 
    <a href="..\wsk\nc-wsk-pfn_wsk_receive_from_event.md">WskReceiveFromEvent</a> event callback
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
    <a href="..\wsk\ns-wsk-_wsk_buf.md">WSK_BUF</a> structure that is pointed to by the 
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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570822">SOCKADDR</a>

<a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544964">CMSGHDR</a>

<a href="..\wsk\nc-wsk-pfn_wsk_send_to.md">WskSendTo</a>

<mshelp:link keywords="netvista.wsk_provider_datagram_dispatch" tabindex="0"><b>
   WSK_PROVIDER_DATAGRAM_DISPATCH</b></mshelp:link>

<a href="..\wsk\ns-wsk-_wsk_buf.md">WSK_BUF</a>

<a href="..\wsk\nc-wsk-pfn_wsk_receive_from_event.md">WskReceiveFromEvent</a>

<a href="..\wsk\nc-wsk-pfn_wsk_control_socket.md">WskControlSocket</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/sio-wsk-set-remote-address">SIO_WSK_SET_REMOTE_ADDRESS</a>

<a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_RECEIVE_FROM callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

