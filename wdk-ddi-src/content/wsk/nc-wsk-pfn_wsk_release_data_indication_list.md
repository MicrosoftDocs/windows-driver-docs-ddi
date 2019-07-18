---
UID: NC:wsk.PFN_WSK_RELEASE_DATA_INDICATION_LIST
title: PFN_WSK_RELEASE_DATA_INDICATION_LIST (wsk.h)
description: The WskRelease function releases a linked list of WSK_DATA_INDICATION structures that was previously retained by a WSK application.
old-location: netvista\wskrelease.htm
tech.root: netvista
ms.assetid: ef42dfc9-f2f5-4799-b090-8e152a4aafcf
ms.date: 05/02/2018
ms.keywords: PFN_WSK_RELEASE_DATA_INDICATION_LIST, PFN_WSK_RELEASE_DATA_INDICATION_LIST callback, WskReleaseDataIndicationList, WskReleaseDataIndicationList callback function [Network Drivers Starting with Windows Vista], netvista.wskrelease, wsk/WskReleaseDataIndicationList, wskref_5e5f5aa8-bcd6-426c-a82c-7fde106f6e8d.xml
ms.topic: callback
f1_keywords:
 - "wsk/WskReleaseDataIndicationList"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wsk.h
api_name:
- WskReleaseDataIndicationList
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# PFN_WSK_RELEASE_DATA_INDICATION_LIST callback function


## -description


The 
  <b>WskRelease</b> function releases a linked list of 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_data_indication">WSK_DATA_INDICATION</a> structures
  that was previously retained by a WSK application.

<b>WskRelease</b> can be declared in two different ways, depending on the type of socket. This topic describes <b>WskRelease</b> for connection-oriented or listening sockets. For datagram sockets, see <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt814377(v=vs.85)">WskRelease (datagram sockets)</a>.


## -parameters




### -param Socket [in]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a> structure that specifies the socket
     object for the socket from which the data was received.


### -param DataIndication [in]

A pointer to the linked list of structures to be released. For this parameter, the WSK application
     should specify the 
     <i>DataIndication</i> parameter that was passed to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_receive_event">WskReceiveEvent</a> or 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_receive_from_event">WskReceiveFromEvent</a> event callback
     function.


## -returns



<b>WskRelease</b> returns one of the following NTSTATUS codes:

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
The list of buffers was successfully released.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified.

</td>
</tr>
</table>
 




## -remarks



For connection-oriented or listening sockets, a WSK application calls the 
    <b>WskRelease</b> function to release a linked list of 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_data_indication">WSK_DATA_INDICATION</a> structures
    that it previously retained by returning STATUS_PENDING from either its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_receive_event">WskReceiveEvent</a> or its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_receive_from_event">WskReceiveFromEvent</a> event callback
    function.

Closing a socket by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a> function does not release
    any outstanding retained linked lists of structures. A WSK application must release all retained linked
    lists of structures before the application calls the 
    <b>WskCloseSocket</b> function to close the socket.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_datagram_indication">WSK_DATAGRAM_INDICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_data_indication">WSK_DATA_INDICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_provider_connection_dispatch">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_provider_stream_dispatch">WSK_PROVIDER_STREAM_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_receive_event">WskReceiveEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_receive_from_event">WskReceiveFromEvent</a>
 

 

