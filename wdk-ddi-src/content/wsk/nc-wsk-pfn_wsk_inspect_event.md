---
UID: NC:wsk.PFN_WSK_INSPECT_EVENT
title: PFN_WSK_INSPECT_EVENT (wsk.h)
description: The WskInspectEvent event callback function notifies a WSK application that an incoming connection request on a listening socket that has conditional accept mode enabled has been received.
old-location: netvista\wskinspectevent.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["PFN_WSK_INSPECT_EVENT callback function"]
ms.keywords: PFN_WSK_INSPECT_EVENT, PFN_WSK_INSPECT_EVENT callback, WskInspectEvent, WskInspectEvent callback function [Network Drivers Starting with Windows Vista], netvista.wskinspectevent, wsk/WskInspectEvent, wskref_096ba538-90c2-454b-9334-d6241425945e.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFN_WSK_INSPECT_EVENT
 - wsk/PFN_WSK_INSPECT_EVENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wsk.h
api_name:
 - WskInspectEvent
---

# PFN_WSK_INSPECT_EVENT callback function


## -description

The 
  <i>WskInspectEvent</i> event callback function notifies a WSK application that an incoming connection
  request on a listening socket that has conditional accept mode enabled has been received.

## -parameters

### -param SocketContext 

[in, optional]
A pointer to the socket context for the listening socket on which the incoming connection request
     was received. The WSK application provided this pointer to the WSK subsystem when it called the 
     <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket">WskSocket</a> function to create the listening
     socket.

### -param LocalAddress 

[in]
A pointer to a buffer that contains the local transport address on which the incoming connection
     request arrived. The buffer contains the specific SOCKADDR structure type that corresponds to the
     address family that the WSK application specified when it created the listening socket.

### -param RemoteAddress 

[in]
A pointer to a buffer that contains the remote transport address from which the incoming
     connection request originated. The buffer contains the specific SOCKADDR structure type that corresponds
     to the address family that the WSK application specified when it created the listening socket.

### -param InspectID 

[in, optional]
A pointer to a 
     <a href="/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_inspect_id">WSK_INSPECT_ID</a> structure. The contents of
     the structure identify the incoming connection request that is being inspected. If this pointer is <b>NULL</b>,
     the listening socket is no longer functional and the WSK application must call the 
     <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a> function to close the
     listening socket as soon as possible.

## -returns

A WSK application's 
     <i>WskInspectEvent</i> event callback function can return one of the following WSK_INSPECT_ACTION
     values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>WskInspectAccept</b></b></dt>
</dl>
</td>
<td width="60%">
The incoming connection request is accepted.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>WskInspectReject</b></b></dt>
</dl>
</td>
<td width="60%">
The incoming connection request is rejected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>WskInspectPend</b></b></dt>
</dl>
</td>
<td width="60%">
The WSK application could not determine if the incoming connection request should be accepted or
       rejected immediately.

</td>
</tr>
</table>

## -remarks

The WSK subsystem calls a WSK application's 
    <i>WskInspectEvent</i> event callback function on a listening socket that has conditional accept mode
    enabled. A WSK application can enable conditional accept mode on a listening socket by enabling the 
    <a href="/windows-hardware/drivers/network/so-conditional-accept">SO_CONDITIONAL_ACCEPT</a> socket option.
    For more information about conditionally accepting incoming connections, see 
    <a href="/windows-hardware/drivers/network/listening-for-and-accepting-incoming-connections">Listening for and
    Accepting Incoming Connections</a>.

If a WSK application returns 
    <b>WskInspectAccept</b> from its 
    <i>WskInspectEvent</i> event callback function, the WSK subsystem continues to establish the socket
    connection. The WSK subsystem returns the socket to the WSK application by either completing a call to
    the 
    <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_accept">WskAccept</a> function, or by calling the WSK
    application's 
    <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_accept_event">WskAcceptEvent</a> event callback function if
    the event callback function is enabled. If the incoming connection request is dropped before the socket
    connection is fully established, the WSK subsystem calls the WSK application's 
    <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_abort_event">WskAbortEvent</a> event callback function.

If a WSK application returns 
    <b>WskInspectReject</b> from its 
    <i>WskInspectEvent</i> event callback function, the incoming connection request is dropped and the socket
    connection is not established.

If a WSK application returns 
    <b>WskInspectPend</b> from its 
    <i>WskInspectEvent</i> event callback function, the application must call the 
    <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_inspect_complete">WskInspectComplete</a> function after it
    has determined whether the incoming connection request should be accepted or rejected (unless the
    incoming connection request is aborted in the meantime). The WSK application must copy the contents of
    the 
    <a href="/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_inspect_id">WSK_INSPECT_ID</a> structure that is pointed to
    by the 
    <i>InspectID</i> parameter to its own WSK_INSPECT_ID structure before returning from the 
    <i>WskInspectEvent</i> event callback function. The WSK application passes a pointer to its own
    WSK_INSPECT_ID structure to the 
    <b>WskInspectComplete</b> function when it completes the inspection. The WSK application also uses this
    structure to identify the incoming connection request if the request is aborted before the inspection is
    complete.

The 
    <a href="/windows/win32/api/ws2def/ns-ws2def-sockaddr">SOCKADDR</a> structures that are pointed to by the 
    <i>LocalAddress</i> and 
    <i>RemoteAddress</i> parameters are valid only for the duration of the call to the 
    <i>WskInspectEvent</i> event callback function. If a WSK application returns 
    <b>WskInspectPend</b> from its 
    <i>WskInspectEvent</i> event callback function and it needs these transport addresses during the remainder
    of the inspection, it must copy the contents of these structures to its own SOCKADDR structures before
    returning from the 
    <i>WskInspectEvent</i> event callback function.

The WSK subsystem calls a WSK application's 
    <i>WskInspectEvent</i> event callback function at IRQL <= DISPATCH_LEVEL.

A WSK application's <i>WskInspectEvent</i> event callback function must not wait for completion of other WSK requests in the context of WSK completion or event callback functions. The callback can initiate other WSK requests (assuming that it doesn't spend too much time at DISPATCH_LEVEL), but it must not wait for their completion even when the callback is called at IRQL = PASSIVE_LEVEL.

## -see-also

<a href="/windows/win32/api/ws2def/ns-ws2def-sockaddr">SOCKADDR</a>



<a href="/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_client_listen_dispatch">WSK_CLIENT_LISTEN_DISPATCH</a>



<a href="/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_inspect_id">WSK_INSPECT_ID</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_abort_event">WskAbortEvent</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_accept">WskAccept</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_accept_event">WskAcceptEvent</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_control_socket">WskControlSocket</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_inspect_complete">WskInspectComplete</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket">WskSocket</a>
