---
UID: NS:wsk._WSK_PROVIDER_LISTEN_DISPATCH
title: "_WSK_PROVIDER_LISTEN_DISPATCH"
author: windows-driver-content
description: The WSK_PROVIDER_LISTEN_DISPATCH structure specifies the WSK subsystem's table of functions for a listening socket.
old-location: netvista\wsk_provider_listen_dispatch.htm
old-project: netvista
ms.assetid: 56df7cb9-9ae7-4249-9583-a9259e604238
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PWSK_PROVIDER_LISTEN_DISPATCH, PWSK_PROVIDER_LISTEN_DISPATCH, PWSK_PROVIDER_LISTEN_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], WSK_PROVIDER_LISTEN_DISPATCH, WSK_PROVIDER_LISTEN_DISPATCH structure [Network Drivers Starting with Windows Vista], _WSK_PROVIDER_LISTEN_DISPATCH, netvista.wsk_provider_listen_dispatch, wsk/PWSK_PROVIDER_LISTEN_DISPATCH, wsk/WSK_PROVIDER_LISTEN_DISPATCH, wskref_f2c1b28d-48f5-4667-bb4e-8dd1d5f25916.xml"
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
-	WSK_PROVIDER_LISTEN_DISPATCH
product: Windows
targetos: Windows
req.typenames: WSK_PROVIDER_LISTEN_DISPATCH, *PWSK_PROVIDER_LISTEN_DISPATCH
req.product: Windows 10 or later.
---

# _WSK_PROVIDER_LISTEN_DISPATCH structure


## -description


The WSK_PROVIDER_LISTEN_DISPATCH structure specifies the WSK subsystem's table of functions for a
  listening socket.


## -syntax


````
typedef struct _WSK_PROVIDER_LISTEN_DISPATCH {
  WSK_PROVIDER_BASIC_DISPATCH Basic;
  PFN_WSK_BIND                WskBind;
  PFN_WSK_ACCEPT              WskAccept;
  PFN_WSK_INSPECT_COMPLETE    WskInspectComplete;
  PFN_WSK_GET_LOCAL_ADDRESS   WskGetLocalAddress;
} WSK_PROVIDER_LISTEN_DISPATCH, *PWSK_PROVIDER_LISTEN_DISPATCH;
````


## -struct-fields




### -field Basic

The members of the 
     <a href="..\wsk\ns-wsk-_wsk_provider_basic_dispatch.md">
     WSK_PROVIDER_BASIC_DISPATCH</a> structure are included as members of the WSK_PROVIDER_LISTEN_DISPATCH
     structure.


### -field WskBind

A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn_wsk_bind.md">WskBind</a> function for the socket.


### -field WskAccept

A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn_wsk_accept.md">WskAccept</a> function for the socket.


### -field WskInspectComplete

A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn_wsk_inspect_complete.md">WskInspectComplete</a> function for the
     socket.


### -field WskGetLocalAddress

A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn_wsk_get_local_address.md">WskGetLocalAddress</a> function for the
     socket.


## -remarks



The member list of the WSK_PROVIDER_LISTEN_DISPATCH structure includes an unnamed 
    <a href="..\wsk\ns-wsk-_wsk_provider_basic_dispatch.md">
    WSK_PROVIDER_BASIC_DISPATCH</a> structure. The compiler that is included with the WDK supports a
    Microsoft-specific extension to the C language that allows unnamed structures within structure
    declarations. The result is that the structure members of the WSK_PROVIDER_BASIC_DISPATCH structure are
    included in the WSK_PROVIDER_LISTEN_DISPATCH structure as if they were native members of the
    WSK_PROVIDER_LISTEN_DISPATCH structure.

A WSK application receives a pointer to a WSK_PROVIDER_LISTEN_DISPATCH structure when the WSK
    application calls the 
    <a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a> function to create a listening socket.
    The pointer is contained in the 
    <b>Dispatch</b> member of the 
    <a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a> structure that is received from the
    WSK subsystem.




## -see-also

<a href="..\wsk\nc-wsk-pfn_wsk_control_socket.md">WskControlSocket</a>



<a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a>



<a href="..\wsk\nc-wsk-pfn_wsk_inspect_complete.md">WskInspectComplete</a>



<a href="..\wsk\nc-wsk-pfn_wsk_accept.md">WskAccept</a>



<a href="..\wsk\ns-wsk-_wsk_client_listen_dispatch.md">WSK_CLIENT_LISTEN_DISPATCH</a>



<a href="..\wsk\nc-wsk-pfn_wsk_bind.md">WskBind</a>



<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>



<a href="..\wsk\ns-wsk-_wsk_provider_basic_dispatch.md">WSK_PROVIDER_BASIC_DISPATCH</a>



<a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_PROVIDER_LISTEN_DISPATCH structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

