---
UID: NC:wsk.PFN_WSK_RELEASE_DATAGRAM_INDICATION_LIST
title: PFN_WSK_RELEASE_DATAGRAM_INDICATION_LIST (wsk.h)
description: The WskRelease function releases a linked list of WSK_DATAGRAM_INDICATION structures that was previously retained by a WSK application.
old-location: netvista\pfn_wsk_release_datagram_indication_list.htm
tech.root: netvista
ms.assetid: 4E186CBD-61BC-4337-81AC-65F6CD7433F3
ms.date: 05/02/2018
ms.keywords: PFN_WSK_RELEASE_DATAGRAM_INDICATION_LIST, PFN_WSK_RELEASE_DATAGRAM_INDICATION_LIST callback, WskReleaseDatagramIndicationList, WskReleaseDatagramIndicationList callback function [Network Drivers Starting with Windows Vista], netvista.pfn_wsk_release_datagram_indication_list, wsk/WskReleaseDatagramIndicationList
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wsk.h
api_name:
- WskReleaseDatagramIndicationList
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# PFN_WSK_RELEASE_DATAGRAM_INDICATION_LIST callback function


## -description


The 
  <b>WskRelease</b> function releases a linked list of 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff571164">WSK_DATAGRAM_INDICATION</a> structures
  that was previously retained by a WSK application.

<b>WskRelease</b> can be declared in two different ways, depending on the type of socket. This topic describes <b>WskRelease</b> for datagram sockets. For connection-oriented or listening sockets, see <a href="https://msdn.microsoft.com/ef42dfc9-f2f5-4799-b090-8e152a4aafcf">WskRelease (connection-oriented or listening sockets)</a>.


## -parameters




### -param Socket [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a> structure that specifies the socket
     object for the socket from which the data was received.


### -param DatagramIndication [in]

A pointer to the linked list of structures to be released. For this parameter, the WSK application
     should specify the 
     <i>DatagramIndication</i> parameter that was passed to its 
     <a href="https://msdn.microsoft.com/2a7a7570-ed26-48be-b27b-dc240588ecfc">WskReceiveEvent</a> or 
     <a href="https://msdn.microsoft.com/1cdb8a70-54fe-44a6-a16c-71cbf6a49ef2">WskReceiveFromEvent</a> event callback
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
The list of structures was successfully released.

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



A WSK application calls the 
    <b>WskRelease</b> function to release a linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff571164">WSK_DATAGRAM_INDICATION</a> structures
    that it previously retained by returning STATUS_PENDING from either its 
    <a href="https://msdn.microsoft.com/2a7a7570-ed26-48be-b27b-dc240588ecfc">WskReceiveEvent</a> or its 
    <a href="https://msdn.microsoft.com/1cdb8a70-54fe-44a6-a16c-71cbf6a49ef2">WskReceiveFromEvent</a> event callback
    function.

Closing a socket by calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571124">WskCloseSocket</a> function does not release
    any outstanding retained linked lists of structures. A WSK application must release all retained linked
    lists of structures before the application calls the 
    <b>WskCloseSocket</b> function to close the socket.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571164">WSK_DATAGRAM_INDICATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571165">WSK_DATA_INDICATION</a>



<a href="https://msdn.microsoft.com/fa8d3395-b800-4e5c-af03-b21520f69158">
   WSK_PROVIDER_DATAGRAM_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571124">WskCloseSocket</a>



<a href="https://msdn.microsoft.com/2a7a7570-ed26-48be-b27b-dc240588ecfc">WskReceiveEvent</a>



<a href="https://msdn.microsoft.com/1cdb8a70-54fe-44a6-a16c-71cbf6a49ef2">WskReceiveFromEvent</a>
 

 

