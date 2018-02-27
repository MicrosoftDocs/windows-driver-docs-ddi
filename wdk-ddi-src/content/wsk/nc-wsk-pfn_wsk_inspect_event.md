---
UID: NC:wsk.PFN_WSK_INSPECT_EVENT
title: PFN_WSK_INSPECT_EVENT
author: windows-driver-content
description: The WskInspectEvent event callback function notifies a WSK application that an incoming connection request on a listening socket that has conditional accept mode enabled has been received.
old-location: netvista\wskinspectevent.htm
old-project: netvista
ms.assetid: 40f184ac-4ef3-485a-a529-71c1f2716427
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PFN_WSK_INSPECT_EVENT, WskInspectEvent, WskInspectEvent callback function [Network Drivers Starting with Windows Vista], netvista.wskinspectevent, wsk/WskInspectEvent, wskref_096ba538-90c2-454b-9334-d6241425945e.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wsk.h
api_name:
-	WskInspectEvent
product: Windows
targetos: Windows
req.typenames: WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO
req.product: Windows 10 or later.
---

# PFN_WSK_INSPECT_EVENT callback


## -description


The 
  <i>WskInspectEvent</i> event callback function notifies a WSK application that an incoming connection
  request on a listening socket that has conditional accept mode enabled has been received.


## -prototype


````
PFN_WSK_INSPECT_EVENT WskInspectEvent;

WSK_INSPECT_ACTION APIENTRY WskInspectEvent(
  _In_opt_ PVOID           SocketContext,
  _In_     PSOCKADDR       LocalAddress,
  _In_     PSOCKADDR       RemoteAddress,
  _In_opt_ PWSK_INSPECT_ID InspectID
)
{ ... }
````


## -parameters




### -param SocketContext [in, optional]

A pointer to the socket context for the listening socket on which the incoming connection request
     was received. The WSK application provided this pointer to the WSK subsystem when it called the 
     <a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a> function to create the listening
     socket.


### -param LocalAddress [in]

A pointer to a buffer that contains the local transport address on which the incoming connection
     request arrived. The buffer contains the specific SOCKADDR structure type that corresponds to the
     address family that the WSK application specified when it created the listening socket.


### -param RemoteAddress [in]

A pointer to a buffer that contains the remote transport address from which the incoming
     connection request originated. The buffer contains the specific SOCKADDR structure type that corresponds
     to the address family that the WSK application specified when it created the listening socket.


### -param InspectID [in, optional]

A pointer to a 
     <a href="..\wsk\ns-wsk-_wsk_inspect_id.md">WSK_INSPECT_ID</a> structure. The contents of
     the structure identify the incoming connection request that is being inspected. If this pointer is <b>NULL</b>,
     the listening socket is no longer functional and the WSK application must call the 
     <a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a> function to close the
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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570829">SO_CONDITIONAL_ACCEPT</a> socket option.
    For more information about conditionally accepting incoming connections, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/listening-for-and-accepting-incoming-connections">Listening for and
    Accepting Incoming Connections</a>.

If a WSK application returns 
    <b>WskInspectAccept</b> from its 
    <i>WskInspectEvent</i> event callback function, the WSK subsystem continues to establish the socket
    connection. The WSK subsystem returns the socket to the WSK application by either completing a call to
    the 
    <a href="..\wsk\nc-wsk-pfn_wsk_accept.md">WskAccept</a> function, or by calling the WSK
    application's 
    <a href="..\wsk\nc-wsk-pfn_wsk_accept_event.md">WskAcceptEvent</a> event callback function if
    the event callback function is enabled. If the incoming connection request is dropped before the socket
    connection is fully established, the WSK subsystem calls the WSK application's 
    <a href="..\wsk\nc-wsk-pfn_wsk_abort_event.md">WskAbortEvent</a> event callback function.

If a WSK application returns 
    <b>WskInspectReject</b> from its 
    <i>WskInspectEvent</i> event callback function, the incoming connection request is dropped and the socket
    connection is not established.

If a WSK application returns 
    <b>WskInspectPend</b> from its 
    <i>WskInspectEvent</i> event callback function, the application must call the 
    <a href="..\wsk\nc-wsk-pfn_wsk_inspect_complete.md">WskInspectComplete</a> function after it
    has determined whether the incoming connection request should be accepted or rejected (unless the
    incoming connection request is aborted in the meantime). The WSK application must copy the contents of
    the 
    <a href="..\wsk\ns-wsk-_wsk_inspect_id.md">WSK_INSPECT_ID</a> structure that is pointed to
    by the 
    <i>InspectID</i> parameter to its own WSK_INSPECT_ID structure before returning from the 
    <i>WskInspectEvent</i> event callback function. The WSK application passes a pointer to its own
    WSK_INSPECT_ID structure to the 
    <b>WskInspectComplete</b> function when it completes the inspection. The WSK application also uses this
    structure to identify the incoming connection request if the request is aborted before the inspection is
    complete.

The 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570822">SOCKADDR</a> structures that are pointed to by the 
    <i>LocalAddress</i> and 
    <i>RemoteAddress</i> parameters are valid only for the duration of the call to the 
    <i>WskInspectEvent</i> event callback function. If a WSK application returns 
    <b>WskInspectPend</b> from its 
    <i>WskInspectEvent</i> event callback function and it needs these transport addresses during the remainder
    of the inspection, it must copy the contents of these structures to its own SOCKADDR structures before
    returning from the 
    <i>WskInspectEvent</i> event callback function.

The WSK subsystem calls a WSK application's 
    <i>WskInspectEvent</i> event callback function at IRQL &lt;= DISPATCH_LEVEL.

A WSK application's <i>WskInspectEvent</i> event callback function must not wait for completion of other WSK requests in the context of WSK completion or event callback functions. The callback can initiate other WSK requests (assuming that it doesn't spend too much time at DISPATCH_LEVEL), but it must not wait for their completion even when the callback is called at IRQL = PASSIVE_LEVEL.




## -see-also

<a href="..\wsk\ns-wsk-_wsk_client_listen_dispatch.md">WSK_CLIENT_LISTEN_DISPATCH</a>



<a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a>



<a href="..\wsk\nc-wsk-pfn_wsk_control_socket.md">WskControlSocket</a>



<a href="..\wsk\nc-wsk-pfn_wsk_inspect_complete.md">WskInspectComplete</a>



<a href="..\wsk\nc-wsk-pfn_wsk_abort_event.md">WskAbortEvent</a>



<a href="..\wsk\nc-wsk-pfn_wsk_accept.md">WskAccept</a>



<a href="..\wsk\ns-wsk-_wsk_inspect_id.md">WSK_INSPECT_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570822">SOCKADDR</a>



<a href="..\wsk\nc-wsk-pfn_wsk_accept_event.md">WskAcceptEvent</a>



<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_INSPECT_EVENT callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

