---
UID: NS:wsk._WSK_CLIENT_LISTEN_DISPATCH
title: "_WSK_CLIENT_LISTEN_DISPATCH"
author: windows-driver-content
description: The WSK_CLIENT_LISTEN_DISPATCH structure specifies a WSK application's dispatch table of event callback functions for a listening socket.
old-location: netvista\wsk_client_listen_dispatch.htm
old-project: netvista
ms.assetid: aaef10f5-2933-4e16-aca6-2277b52fb174
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "_WSK_CLIENT_LISTEN_DISPATCH, PWSK_CLIENT_LISTEN_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], PWSK_CLIENT_LISTEN_DISPATCH, WSK_CLIENT_LISTEN_DISPATCH structure [Network Drivers Starting with Windows Vista], wsk/PWSK_CLIENT_LISTEN_DISPATCH, netvista.wsk_client_listen_dispatch, wskref_38021620-217a-4a26-b461-f59f87c9579d.xml, *PWSK_CLIENT_LISTEN_DISPATCH, wsk/WSK_CLIENT_LISTEN_DISPATCH, WSK_CLIENT_LISTEN_DISPATCH"
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wsk.h
apiname:
-	WSK_CLIENT_LISTEN_DISPATCH
product: Windows
targetos: Windows
req.typenames: "*PWSK_CLIENT_LISTEN_DISPATCH, WSK_CLIENT_LISTEN_DISPATCH"
req.product: Windows 10 or later.
---

# _WSK_CLIENT_LISTEN_DISPATCH structure


## -description


The WSK_CLIENT_LISTEN_DISPATCH structure specifies a WSK application's dispatch table of event
  callback functions for a listening socket.


## -syntax


````
typedef struct _WSK_CLIENT_LISTEN_DISPATCH {
  PFN_WSK_ACCEPT_EVENT  WskAcceptEvent;
  PFN_WSK_INSPECT_EVENT WskInspectEvent;
  PFN_WSK_ABORT_EVENT   WskAbortEvent;
} WSK_CLIENT_LISTEN_DISPATCH, *PWSK_CLIENT_LISTEN_DISPATCH;
````


## -struct-fields




### -field WskAcceptEvent

A pointer to the WSK application's 
     <a href="..\wsk\nc-wsk-pfn_wsk_accept_event.md">WskAcceptEvent</a> event callback function for
     the socket. If the WSK application does not enable the 
     <i>WskAcceptEvent</i> event callback function for the socket, this pointer can be <b>NULL</b>.


### -field WskInspectEvent

A pointer to the WSK application's 
     <a href="..\wsk\nc-wsk-pfn_wsk_inspect_event.md">WskInspectEvent</a> event callback function
     for the socket. If the WSK application does not enable conditional accept mode for the socket, this
     pointer can be <b>NULL</b>.


### -field WskAbortEvent

A pointer to the WSK application's 
     <a href="..\wsk\nc-wsk-pfn_wsk_abort_event.md">WskAbortEvent</a> event callback function for
     the socket. If the WSK application does not enable conditional accept mode for the socket, this pointer
     can be <b>NULL</b>.


## -remarks



A WSK application passes a pointer to a WSK_CLIENT_LISTEN_DISPATCH structure to the WSK subsystem when
    the WSK application calls the 
    <a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a> function to create a listening
    socket.




## -see-also

<a href="..\wsk\nc-wsk-pfn_wsk_accept_event.md">WskAcceptEvent</a>



<a href="..\wsk\nc-wsk-pfn_wsk_inspect_event.md">WskInspectEvent</a>



<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>



<a href="..\wsk\ns-wsk-_wsk_provider_listen_dispatch.md">WSK_PROVIDER_LISTEN_DISPATCH</a>



<a href="..\wsk\nc-wsk-pfn_wsk_abort_event.md">WskAbortEvent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_CLIENT_LISTEN_DISPATCH structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

