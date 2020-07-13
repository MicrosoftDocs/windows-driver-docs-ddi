---
UID: NC:wsk.PFN_WSK_DISCONNECT_EVENT
title: PFN_WSK_DISCONNECT_EVENT (wsk.h)
description: The WskDisconnectEvent event callback function notifies a WSK application that a connection on a connection-oriented socket has been disconnected by the remote application.
old-location: netvista\wskdisconnectevent.htm
tech.root: netvista
ms.assetid: bf12d7b3-080e-46d9-b276-76d42068e7c6
ms.date: 05/02/2018
keywords: ["PFN_WSK_DISCONNECT_EVENT callback function"]
ms.keywords: PFN_WSK_DISCONNECT_EVENT, PFN_WSK_DISCONNECT_EVENT callback, WskDisconnectEvent, WskDisconnectEvent callback function [Network Drivers Starting with Windows Vista], netvista.wskdisconnectevent, wsk/WskDisconnectEvent, wskref_ec112b8d-f939-456f-9766-e181c7836e2c.xml
f1_keywords:
 - "wsk/WskDisconnectEvent"
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
- WskDisconnectEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_WSK_DISCONNECT_EVENT callback function


## -description


The 
  <i>WskDisconnectEvent</i> event callback function notifies a WSK application that a connection on a
  connection-oriented socket has been disconnected by the remote application.


## -parameters




### -param SocketContext [in, optional]

A pointer to the socket context for the connection-oriented socket that has been disconnected. The
     WSK application provided this pointer to the WSK subsystem in one of the following ways:
     

<ul>
<li>
It called the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket">WskSocket</a> function to create the socket.

</li>
<li>
It called the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket_connect">WskSocketConnect</a> function to create
       the socket.

</li>
<li>
It called the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_accept">WskAccept</a> function to accept the socket as an
       incoming connection.

</li>
<li>
Its 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_accept_event">WskAcceptEvent</a> event callback function
       was called to accept the socket as an incoming connection.

</li>
</ul>

### -param Flags [in]

A ULONG value that contains a bitwise OR of a combination of the following flags:
     





#### WSK_FLAG_ABORTIVE

The remote application performed an abortive disconnect of the socket. If this flag is not set,
       the remote application performed a graceful disconnect of the socket.



#### WSK_FLAG_AT_DISPATCH_LEVEL

The WSK subsystem called the 
       <i>WskDisconnectEvent</i> event callback function at IRQL = DISPATCH_LEVEL. If this flag is not set,
       the WSK subsystem might have called the 
       <i>WskDisconnectEvent</i> event callback function at any IRQL <= DISPATCH_LEVEL.


## -returns



A WSK application's 
     <i>WskDisconnectEvent</i> event callback function must always return STATUS_SUCCESS.




## -remarks



The WSK subsystem calls a WSK application's 
    <i>WskDisconnectEvent</i> event callback function when a connection-oriented socket is disconnected by the
    remote application only if the event callback function was previously enabled with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/so-wsk-event-callback">SO_WSK_EVENT_CALLBACK</a> socket option.
    For more information about enabling a socket's event callback functions, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/enabling-and-disabling-event-callback-functions">Enabling and
    Disabling Event Callback Functions</a>.

If the remote application performed a graceful disconnect of the socket, no further data will be
    received from the socket. However, the WSK application can still send data to the socket until the socket
    is either completely closed by the remote application or the WSK application calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_disconnect">WskDisconnect</a> function or the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a> function on the socket.

If the remote application performed an abortive disconnect of the socket, no further data will be
    received from the socket and no further data can be sent to the socket.

The WSK subsystem calls a WSK application's 
    <i>WskDisconnectEvent</i> event callback function at IRQL <= DISPATCH_LEVEL.

A WSK application's <i>WskDisconnectEvent</i> event callback function must not wait for completion of other WSK requests in the context of WSK completion or event callback functions. The callback can initiate other WSK requests (assuming that it doesn't spend too much time at DISPATCH_LEVEL), but it must not wait for their completion even when the callback is called at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_client_connection_dispatch">
   WSK_CLIENT_CONNECTION_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_accept">WskAccept</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_accept_event">WskAcceptEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_connect">WskConnect</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_control_socket">WskControlSocket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_disconnect">WskDisconnect</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket">WskSocket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket_connect">WskSocketConnect</a>
 

 

