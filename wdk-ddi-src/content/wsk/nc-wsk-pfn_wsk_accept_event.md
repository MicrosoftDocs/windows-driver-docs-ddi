---
UID: NC:wsk.PFN_WSK_ACCEPT_EVENT
title: PFN_WSK_ACCEPT_EVENT (wsk.h)
description: The WskAcceptEvent event callback function notifies a WSK application that an incoming connection on a listening socket has been accepted.
old-location: netvista\wskacceptevent.htm
tech.root: netvista
ms.assetid: 672440f0-810a-4e68-82a5-d038770898c5
ms.date: 05/02/2018
ms.keywords: PFN_WSK_ACCEPT_EVENT, PFN_WSK_ACCEPT_EVENT callback, WskAcceptEvent, WskAcceptEvent callback function [Network Drivers Starting with Windows Vista], netvista.wskacceptevent, wsk/WskAcceptEvent, wskref_5a830348-5fa7-4704-86f2-9d1a953f057b.xml
ms.topic: callback
f1_keywords:
 - "wsk/WskAcceptEvent"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- wsk.h
api_name:
- WskAcceptEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_WSK_ACCEPT_EVENT callback function


## -description


The 
  <i>WskAcceptEvent</i> event callback function notifies a WSK application that an incoming connection on a
  listening socket has been accepted.


## -parameters




### -param SocketContext [in, optional]

A pointer to the socket context for the listening socket on which the incoming connection was
     accepted. The WSK application provided this pointer to the WSK subsystem when it called the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket">WskSocket</a> function to create the listening
     socket.


### -param Flags [in]

A ULONG value that contains the following flag, or zero:
     





#### WSK_FLAG_AT_DISPATCH_LEVEL

The WSK subsystem called the 
       <i>WskAcceptEvent</i> event callback function at IRQL = DISPATCH_LEVEL. If this flag is not set, the
       WSK subsystem might have called the 
       <i>WskAcceptEvent</i> event callback function at any IRQL <= DISPATCH_LEVEL.


### -param LocalAddress [in]

A pointer to a buffer that contains the local transport address on which the incoming connection
     arrived. The buffer contains the specific SOCKADDR structure type that corresponds to the address family
     that the WSK application specified when it created the listening socket.


### -param RemoteAddress [in]

A pointer to a buffer that contains the remote transport address from which the incoming
     connection originated. The buffer contains the specific SOCKADDR structure type that corresponds to the
     address family that the WSK application specified when it created the listening socket.


### -param AcceptSocket [in, optional]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a> structure that is the socket object
     for the accepted socket. If this pointer is <b>NULL</b>, the listening socket is no longer functional and the
     WSK application must call the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a> function to close the
     listening socket as soon as possible.


### -param *AcceptSocketContext [out]

A pointer to a variable that receives a pointer to a WSK application-supplied context for the
     socket that is being accepted. The WSK subsystem passes this pointer to the accepted socket's event
     callback functions. The context information is opaque to the WSK subsystem and must be stored in
     non-paged memory. If the WSK application will not be enabling any event callback functions on the
     accepted socket, the application should set the variable that is pointed to by the 
     <i>AcceptSocketContext</i> parameter to <b>NULL</b>.


#### - **AcceptSocketDispatch [out]

A pointer to a variable that receives a pointer to a constant 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_client_connection_dispatch">
     WSK_CLIENT_CONNECTION_DISPATCH</a> structure. This structure is a dispatch table that contains
     pointers to the event callback functions for the accepted socket. If the WSK application will not be
     enabling all of the event callback functions for the accepted socket, the application should set the
     pointers in the dispatch table to <b>NULL</b> for those event callback functions that it does not enable. If
     the WSK application will not be enabling any event callback functions on the accepted socket, it should
     set the variable that is pointed to by the 
     <i>AcceptSocketDispatch</i> parameter to <b>NULL</b>.


#### - AcceptSocketDispatch [out]

A pointer to a variable that receives a pointer to a constant 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_client_connection_dispatch">
     WSK_CLIENT_CONNECTION_DISPATCH</a> structure. This structure is a dispatch table that contains
     pointers to the event callback functions for the accepted socket. If the WSK application will not be
     enabling all of the event callback functions for the accepted socket, the application should set the
     pointers in the dispatch table to <b>NULL</b> for those event callback functions that it does not enable. If
     the WSK application will not be enabling any event callback functions on the accepted socket, it should
     set the variable that is pointed to by the 
     <i>AcceptSocketDispatch</i> parameter to <b>NULL</b>.


## -returns



A WSK application's 
     <i>WskAcceptEvent</i> event callback function can return one of the following NTSTATUS codes:

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
The WSK application accepted the incoming connection.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REQUEST_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
The WSK application rejected the incoming connection. If this value is returned, the WSK
       subsystem will close the accepted socket on behalf of the WSK application.

</td>
</tr>
</table>
 




## -remarks



The WSK subsystem calls a WSK application's 
    <i>WskAcceptEvent</i> event callback function when an incoming connection is accepted on the listening
    socket only if the event callback function was previously enabled with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/so-wsk-event-callback">SO_WSK_EVENT_CALLBACK</a> socket option.
    For more information about enabling a socket's event callback functions, see 
    <a href="https://docs.microsoft.com/windows/desktop/api/evntprov/nc-evntprov-penablecallback">Enabling and
    Disabling Event Callback Functions</a>.

If a WSK application's 
    <i>WskAcceptEvent</i> event callback function is enabled on a listening socket and the application has a
    pending call to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_accept">WskAccept</a> function on the same listening socket,
    then, when an incoming connection arrives, the pending call to 
    <b>WskAccept</b> takes precedence over the 
    <i>WskAcceptEvent</i> event callback function. The WSK subsystem calls the application's 
    <i>WskAcceptEvent</i> event callback function only if there are no IRPs queued from pending calls to the 
    <b>WskAccept</b> function. However, a WSK application should not assume that the WSK subsystem will not
    call the application's 
    <i>WskAcceptEvent</i> event callback function for a listening socket that has a pending call to the 
    <b>WskAccept</b> function. Race conditions exist where the WSK subsystem could still call the WSK
    application's 
    <i>WskAcceptEvent</i> event callback function for the socket. The only way for a WSK application to ensure
    that the WSK subsystem will not call the application's 
    <i>WskAcceptEvent</i> event callback function for a listening socket is to disable the application's 
    <i>WskAcceptEvent</i> event callback function on the socket.

When the WSK subsystem calls a WSK application's 
    <i>WskAcceptEvent</i> event callback function, all of the event callback functions on the accepted socket
    are disabled by default. If a WSK application enables any of the connection-oriented socket event
    callback functions on a listening socket, those event callback functions will be enabled by default on
    all connection-oriented sockets that are accepted on that listening socket. For more information about
    enabling any of the accepted socket's event callback functions, see 
    <a href="https://docs.microsoft.com/windows/desktop/api/evntprov/nc-evntprov-penablecallback">Enabling and
    Disabling Event Callback Functions</a>.

The 
    <a href="https://docs.microsoft.com/windows/desktop/api/ws2def/ns-ws2def-sockaddr">SOCKADDR</a> structures that are pointed to by the 
    <i>LocalAddress</i> and 
    <i>RemoteAddress</i> parameters are valid only for the duration of the call to the 
    <i>WskAcceptEvent</i> event callback function. If a WSK application needs these transport addresses at a
    later time, it can copy the contents of these structures to its own SOCKADDR structures before returning
    from the 
    <i>WskAcceptEvent</i> event callback function, or it can later call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_get_local_address">WskGetLocalAddress</a> and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_get_remote_address">WskGetRemoteAddress</a> functions on the
    accepted socket.

The WSK subsystem allocates the memory for the socket object structure (
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a>) for the accepted connection on
    behalf of the WSK application. The WSK subsystem deallocates this memory when the socket is closed.

The WSK subsystem calls a WSK application's 
    <i>WskAcceptEvent</i> event callback function at IRQL <= DISPATCH_LEVEL.

A WSK application's <i>WskAcceptEvent</i> event callback function must not wait for completion of other WSK requests in the context of WSK completion or event callback functions. The callback can initiate other WSK requests (assuming that it doesn't spend too much time at DISPATCH_LEVEL), but it must not wait for their completion even when the callback is called at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ws2def/ns-ws2def-sockaddr">SOCKADDR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_client_connection_dispatch">
   WSK_CLIENT_CONNECTION_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_client_listen_dispatch">WSK_CLIENT_LISTEN_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_accept">WskAccept</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_control_socket">WskControlSocket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_get_local_address">WskGetLocalAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_get_remote_address">WskGetRemoteAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket">WskSocket</a>
 

 

