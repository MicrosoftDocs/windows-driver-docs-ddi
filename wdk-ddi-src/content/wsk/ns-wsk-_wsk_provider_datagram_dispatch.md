---
UID: NS:wsk._WSK_PROVIDER_DATAGRAM_DISPATCH
title: _WSK_PROVIDER_DATAGRAM_DISPATCH
author: windows-driver-content
description: The WSK_PROVIDER_DATAGRAM_DISPATCH structure specifies the WSK subsystem's table of functions for a datagram socket.
old-location: netvista\wsk_provider_datagram_dispatch.htm
old-project: netvista
ms.assetid: fa8d3395-b800-4e5c-af03-b21520f69158
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.wsk_provider_datagram_dispatch, PWSK_PROVIDER_DATAGRAM_DISPATCH, *PWSK_PROVIDER_DATAGRAM_DISPATCH, wsk/WSK_PROVIDER_DATAGRAM_DISPATCH, PWSK_PROVIDER_DATAGRAM_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], WSK_PROVIDER_DATAGRAM_DISPATCH structure [Network Drivers Starting with Windows Vista], wsk/PWSK_PROVIDER_DATAGRAM_DISPATCH, WSK_PROVIDER_DATAGRAM_DISPATCH, wskref_20703414-7e22-4163-8d24-0ddec03672b6.xml, _WSK_PROVIDER_DATAGRAM_DISPATCH
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	wsk.h
apiname: 
-	WSK_PROVIDER_DATAGRAM_DISPATCH
product: Windows
targetos: Windows
req.typenames: *PWSK_PROVIDER_DATAGRAM_DISPATCH, WSK_PROVIDER_DATAGRAM_DISPATCH
req.product: Windows 10 or later.
---

# _WSK_PROVIDER_DATAGRAM_DISPATCH structure


## -description


The WSK_PROVIDER_DATAGRAM_DISPATCH structure specifies the WSK subsystem's table of functions for a
  datagram socket.


## -syntax


````
typedef struct _WSK_PROVIDER_DATAGRAM_DISPATCH {
  WSK_PROVIDER_BASIC_DISPATCH              Basic;
  PFN_WSK_BIND                             WskBind;
  PFN_WSK_SEND_TO                          WskSendTo;
  PFN_WSK_RECEIVE_FROM                     WskReceiveFrom;
  PFN_WSK_RELEASE_DATAGRAM_INDICATION_LIST WskRelease;
  PFN_WSK_GET_LOCAL_ADDRESS                WskGetLocalAddress;
} WSK_PROVIDER_DATAGRAM_DISPATCH, *PWSK_PROVIDER_DATAGRAM_DISPATCH;
````


## -struct-fields




### -field Basic

The members of the 
     <mshelp:link keywords="netvista.wsk_provider_basic_dispatch" tabindex="0"><b>
     WSK_PROVIDER_BASIC_DISPATCH</b></mshelp:link> structure are included as members of the
     WSK_PROVIDER_DATAGRAM_DISPATCH structure.


### -field WskBind

A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn_wsk_bind.md">WskBind</a> function for the socket.


### -field WskSendTo

A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn_wsk_send_to.md">WskSendTo</a> function for the socket.


### -field WskReceiveFrom

A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn_wsk_receive_from.md">WskReceiveFrom</a> function for the
     socket.


### -field WskRelease

A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn_wsk_release_data_indication_list.md">WskRelease</a> function for the socket.


### -field WskGetLocalAddress

A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn_wsk_get_local_address.md">WskGetLocalAddress</a> function for the
     socket.


### -field WskSendMessages

 



## -remarks


The member list of the WSK_PROVIDER_DATAGRAM_DISPATCH structure includes an unnamed 
    <mshelp:link keywords="netvista.wsk_provider_basic_dispatch" tabindex="0"><b>
    WSK_PROVIDER_BASIC_DISPATCH</b></mshelp:link> structure. The compiler that is included with the WDK supports a
    Microsoft-specific extension to the C language that allows unnamed structures within structure
    declarations. The result is that the structure members of the WSK_PROVIDER_BASIC_DISPATCH structure are
    included in the WSK_PROVIDER_DATAGRAM_DISPATCH structure as if they were native members of the
    WSK_PROVIDER_DATAGRAM_DISPATCH structure.

A WSK application receives a pointer to a WSK_PROVIDER_DATAGRAM_DISPATCH structure when the WSK
    application calls the 
    <a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a> function to create a datagram socket.
    The pointer is contained in the 
    <b>Dispatch</b> member of the 
    <a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a> structure that is received from the
    WSK subsystem .



## -see-also

<a href="..\wsk\nc-wsk-pfn_wsk_release_data_indication_list.md">WskRelease</a>

<a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a>

<a href="..\wsk\nc-wsk-pfn_wsk_receive_from.md">WskReceiveFrom</a>

<a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a>

<a href="..\wsk\nc-wsk-pfn_wsk_send_to.md">WskSendTo</a>

<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>

<a href="..\wsk\nc-wsk-pfn_wsk_bind.md">WskBind</a>

<a href="..\wsk\ns-wsk-_wsk_provider_basic_dispatch.md">WSK_PROVIDER_BASIC_DISPATCH</a>

<a href="..\wsk\nc-wsk-pfn_wsk_control_socket.md">WskControlSocket</a>

<a href="..\wsk\ns-wsk-_wsk_client_datagram_dispatch.md">WSK_CLIENT_DATAGRAM_DISPATCH</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_PROVIDER_DATAGRAM_DISPATCH structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

