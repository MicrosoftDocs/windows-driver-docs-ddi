---
UID: NS:wsk._WSK_CLIENT_CONNECTION_DISPATCH
title: _WSK_CLIENT_CONNECTION_DISPATCH (wsk.h)
description: The WSK_CLIENT_CONNECTION_DISPATCH structure specifies a WSK application's dispatch table of event callback functions for a connection-oriented socket.
old-location: netvista\wsk_client_connection_dispatch.htm
tech.root: netvista
ms.assetid: 960eee8a-2950-4baf-b32d-be13b3d65951
ms.date: 05/02/2018
keywords: ["WSK_CLIENT_CONNECTION_DISPATCH structure"]
ms.keywords: "*PWSK_CLIENT_CONNECTION_DISPATCH, PWSK_CLIENT_CONNECTION_DISPATCH, PWSK_CLIENT_CONNECTION_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], WSK_CLIENT_CONNECTION_DISPATCH, WSK_CLIENT_CONNECTION_DISPATCH structure [Network Drivers Starting with Windows Vista], _WSK_CLIENT_CONNECTION_DISPATCH, netvista.wsk_client_connection_dispatch, wsk/PWSK_CLIENT_CONNECTION_DISPATCH, wsk/WSK_CLIENT_CONNECTION_DISPATCH, wskref_2fd26ffb-dab8-4529-9fd0-6043509312c9.xml"
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
req.irql: 
targetos: Windows
req.typenames: WSK_CLIENT_CONNECTION_DISPATCH, *PWSK_CLIENT_CONNECTION_DISPATCH
f1_keywords:
 - _WSK_CLIENT_CONNECTION_DISPATCH
 - wsk/_WSK_CLIENT_CONNECTION_DISPATCH
 - PWSK_CLIENT_CONNECTION_DISPATCH
 - wsk/PWSK_CLIENT_CONNECTION_DISPATCH
 - WSK_CLIENT_CONNECTION_DISPATCH
 - wsk/WSK_CLIENT_CONNECTION_DISPATCH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wsk.h
api_name:
 - WSK_CLIENT_CONNECTION_DISPATCH
---

# _WSK_CLIENT_CONNECTION_DISPATCH structure


## -description

The WSK_CLIENT_CONNECTION_DISPATCH structure specifies a WSK application's dispatch table of event
  callback functions for a connection-oriented socket.

## -struct-fields

### -field WskReceiveEvent

A pointer to the WSK application's 
     <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_receive_event">WskReceiveEvent</a> event callback function
     for the socket. If the WSK application does not enable the 
     <i>WskReceiveEvent</i> event callback function for the socket, this pointer can be <b>NULL</b>.

### -field WskDisconnectEvent

A pointer to the WSK application's 
     <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_disconnect_event">WskDisconnectEvent</a> event callback
     function for the socket. If the WSK application does not enable the 
     <i>WskDisconnectEvent</i> event callback function for the socket, this pointer can be <b>NULL</b>.

### -field WskSendBacklogEvent

A pointer to the WSK application's 
     <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_send_backlog_event">WskSendBacklogEvent</a> event callback
     function for the socket. If the WSK application does not enable the 
     <i>WskSendBacklogEvent</i> event callback function for the socket, this pointer can be <b>NULL</b>.

## -remarks

A WSK application passes a pointer to a WSK_CLIENT_CONNECTION_DISPATCH structure to the WSK subsystem
    in one of the following ways:

<ul>
<li>
When calling the 
      <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket">WskSocket</a> function to create a
      connection-oriented socket.

</li>
<li>
When calling the 
      <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket_connect">WskSocketConnect</a> function to create,
      bind, and connect a connection-oriented socket.

</li>
<li>
When calling the 
      <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_accept">WskAccept</a> function to accept an incoming
      connection-oriented socket on a listening socket.

</li>
<li>
As a returned parameter when the WSK subsystem calls the WSK application's 
      <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_accept_event">WskAcceptEvent</a> event callback function.
      The WSK subsystem calls a WSK application's 
      <i>WskAcceptEvent</i> event callback function to notify the WSK application that an incoming
      connection-oriented socket has been accepted on a listening socket.

</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_connection_dispatch">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_accept">WskAccept</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_accept_event">WskAcceptEvent</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_disconnect_event">WskDisconnectEvent</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_receive_event">WskReceiveEvent</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_send_backlog_event">WskSendBacklogEvent</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket">WskSocket</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket_connect">WskSocketConnect</a>