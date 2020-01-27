---
UID: NC:wsk.PFN_WSK_SEND_BACKLOG_EVENT
title: PFN_WSK_SEND_BACKLOG_EVENT (wsk.h)
description: The WskSendBacklogEvent event callback function notifies a WSK application when the ideal send backlog size changes for a connection-oriented socket.
old-location: netvista\wsksendbacklogevent.htm
tech.root: netvista
ms.assetid: e944af6f-6753-48b0-b3f6-0709f24e3ff0
ms.date: 05/02/2018
ms.keywords: PFN_WSK_SEND_BACKLOG_EVENT, PFN_WSK_SEND_BACKLOG_EVENT callback, WskSendBacklogEvent, WskSendBacklogEvent callback function [Network Drivers Starting with Windows Vista], netvista.wsksendbacklogevent, wsk/WskSendBacklogEvent, wskref_9b34fa29-9c3a-4aa2-8ceb-3f637c4902cd.xml
f1_keywords:
 - "wsk/WskSendBacklogEvent"
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
- WskSendBacklogEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_WSK_SEND_BACKLOG_EVENT callback function


## -description


The 
  <i>WskSendBacklogEvent</i> event callback function notifies a WSK application when the ideal send backlog
  size changes for a connection-oriented socket.


## -parameters




### -param SocketContext [in, optional]

A pointer to the socket context for the connection-oriented socket that is notifying the WSK
     application about a change to its ideal send backlog size. The WSK application provided this pointer to
     the WSK subsystem in one of the following ways:
     

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

### -param IdealBacklogSize [in]

A variable that contains the new ideal send backlog size.


## -returns



A WSK application's 
     <i>WskSendBacklogEvent</i> event callback function must always return STATUS_SUCCESS.




## -remarks



The WSK subsystem calls a WSK application's 
    <i>WskSendBacklogEvent</i> event callback function when the ideal send backlog size changes for a
    connection-oriented socket only if the event callback function was previously enabled with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/so-wsk-event-callback">SO_WSK_EVENT_CALLBACK</a> socket option.
    For more information about enabling a socket's event callback functions, see 
    <a href="https://docs.microsoft.com/windows/desktop/api/evntprov/nc-evntprov-penablecallback">Enabling and
    Disabling Event Callback Functions</a>.

The ideal send backlog size for a connection-oriented socket is the optimal amount of send data that
    needs to be kept outstanding (that is, passed to the WSK subsystem but not yet completed) to keep the
    socket's data stream full at all times. A WSK application can use this size to incrementally probe and
    lock the buffers of data to be sent based on the underlying connection's flow control state.

A WSK application can obtain the current ideal backlog size for a connection-oriented socket at any
    time by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_control_socket">WskControlSocket</a> function.

The WSK subsystem calls a WSK application's 
    <i>WskSendBacklogEvent</i> event callback function at IRQL <= DISPATCH_LEVEL.

A WSK application's <i>WskSendBacklogEvent</i> event callback function must not wait for completion of other WSK requests in the context of WSK completion or event callback functions. The callback can initiate other WSK requests (assuming that it doesn't spend too much time at DISPATCH_LEVEL), but it must not wait for their completion even when the callback is called at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_client_connection_dispatch">
   WSK_CLIENT_CONNECTION_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_accept">WskAccept</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_accept_event">WskAcceptEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_control_socket">WskControlSocket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_send">WskSend</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket">WskSocket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket_connect">WskSocketConnect</a>
 

 

