---
UID: NS:wsk._WSK_PROVIDER_BASIC_DISPATCH
title: "_WSK_PROVIDER_BASIC_DISPATCH"
author: windows-driver-content
description: The WSK_PROVIDER_BASIC_DISPATCH structure specifies the WSK subsystem's dispatch table of functions for a basic socket.
old-location: netvista\wsk_provider_basic_dispatch.htm
old-project: netvista
ms.assetid: 15cd5336-fe29-4a59-8071-04c802552a5a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWSK_PROVIDER_BASIC_DISPATCH, PWSK_PROVIDER_BASIC_DISPATCH, PWSK_PROVIDER_BASIC_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], WSK_PROVIDER_BASIC_DISPATCH, WSK_PROVIDER_BASIC_DISPATCH structure [Network Drivers Starting with Windows Vista], _WSK_PROVIDER_BASIC_DISPATCH, netvista.wsk_provider_basic_dispatch, wsk/PWSK_PROVIDER_BASIC_DISPATCH, wsk/WSK_PROVIDER_BASIC_DISPATCH, wskref_eac2fecd-6800-4c2f-b636-bcc103c99377.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wsk.h
api_name:
-	WSK_PROVIDER_BASIC_DISPATCH
product: Windows
targetos: Windows
req.typenames: WSK_PROVIDER_BASIC_DISPATCH, *PWSK_PROVIDER_BASIC_DISPATCH
req.product: Windows 10 or later.
---

# _WSK_PROVIDER_BASIC_DISPATCH structure


## -description


The WSK_PROVIDER_BASIC_DISPATCH structure specifies the WSK subsystem's dispatch table of functions
  for a basic socket.


## -syntax


````
typedef struct _WSK_PROVIDER_BASIC_DISPATCH {
  PFN_WSK_CONTROL_SOCKET WskControlSocket;
  PFN_WSK_CLOSE_SOCKET   WskCloseSocket;
} WSK_PROVIDER_BASIC_DISPATCH, *PWSK_PROVIDER_BASIC_DISPATCH;
````


## -struct-fields




### -field WskControlSocket

A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn_wsk_control_socket.md">WskControlSocket</a> function for the
     socket.


### -field WskCloseSocket

A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a> function for the
     socket.


## -remarks



A WSK application receives a pointer to a WSK_PROVIDER_BASIC_DISPATCH structure when the WSK
    application calls the 
    <a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a> function to create a basic socket. The
    pointer is contained in the 
    <b>Dispatch</b> member of the 
    <a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a> structure that is received from the
    WSK subsystem.

The WSK_PROVIDER_BASIC_DISPATCH structure is also included in the 
    <a href="..\wsk\ns-wsk-_wsk_provider_connection_dispatch.md">
    WSK_PROVIDER_CONNECTION_DISPATCH</a>, 
    <a href="..\wsk\ns-wsk-_wsk_provider_datagram_dispatch.md">
    WSK_PROVIDER_DATAGRAM_DISPATCH</a>, and 
    <a href="..\wsk\ns-wsk-_wsk_provider_listen_dispatch.md">
    WSK_PROVIDER_LISTEN_DISPATCH</a> structures. The 
    <a href="..\wsk\nc-wsk-pfn_wsk_control_socket.md">WskControlSocket</a> and 
    <a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a> functions that are included
    in the WSK_PROVIDER_BASIC_DISPATCH structure are supported by all of the 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/winsock-kernel-socket-categories">socket categories</a>.




## -see-also

<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>



<a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a>



<a href="..\wsk\ns-wsk-_wsk_provider_listen_dispatch.md">WSK_PROVIDER_LISTEN_DISPATCH</a>



<a href="..\wsk\ns-wsk-_wsk_provider_datagram_dispatch.md">
   WSK_PROVIDER_DATAGRAM_DISPATCH</a>



<a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a>



<a href="..\wsk\nc-wsk-pfn_wsk_control_socket.md">WskControlSocket</a>



<a href="..\wsk\ns-wsk-_wsk_provider_connection_dispatch.md">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>



 

 


