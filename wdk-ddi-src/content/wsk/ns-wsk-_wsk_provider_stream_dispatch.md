---
UID: NS:wsk._WSK_PROVIDER_STREAM_DISPATCH
title: _WSK_PROVIDER_STREAM_DISPATCH (wsk.h)
description: The WSK_PROVIDER_STREAM_DISPATCH structure specifies the WSK subsystem's table of functions for a stream socket.
old-location: netvista\wsk_provider_stream_dispatch.htm
tech.root: netvista
ms.assetid: A10B901E-9987-40E9-976B-4CD9455E0AEE
ms.date: 05/02/2018
keywords: ["_WSK_PROVIDER_STREAM_DISPATCH structure"]
ms.keywords: "*PWSK_PROVIDER_STREAM_DISPATCH, PWSK_PROVIDER_STREAM_DISPATCH, PWSK_PROVIDER_STREAM_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], WSK_PROVIDER_STREAM_DISPATCH, WSK_PROVIDER_STREAM_DISPATCH structure [Network Drivers Starting with Windows Vista], _WSK_PROVIDER_STREAM_DISPATCH, netvista.wsk_provider_stream_dispatch, wsk/PWSK_PROVIDER_STREAM_DISPATCH, wsk/WSK_PROVIDER_STREAM_DISPATCH"
f1_keywords:
 - "wsk/WSK_PROVIDER_STREAM_DISPATCH"
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wsk.h
api_name:
- WSK_PROVIDER_STREAM_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: WSK_PROVIDER_STREAM_DISPATCH, *PWSK_PROVIDER_STREAM_DISPATCH
---

# _WSK_PROVIDER_STREAM_DISPATCH structure


## -description


The WSK_PROVIDER_STREAM_DISPATCH structure specifies the WSK subsystem's table of functions for a
  stream socket.
   
  


## -struct-fields




### -field Basic

The members of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_basic_dispatch">
     WSK_PROVIDER_BASIC_DISPATCH</a> structure are included as members of the WSK_PROVIDER_STREAM_DISPATCH
     structure.


### -field WskBind

A pointer to the WSK subsystem's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_bind">WskBind</a> function for the socket.


### -field WskAccept

A pointer to the WSK subsystem's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_accept">WskAccept</a> function for the socket.


### -field WskConnect

A pointer to the WSK subsystem's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_connect">WskConnect</a> function for the socket.


### -field WskListen

A pointer to the WSK subsystem's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_listen">WskListen</a> function for the socket.


### -field WskSend

A pointer to the WSK subsystem's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_send">WskSend</a> function for the socket.


### -field WskReceive

A pointer to the WSK subsystem's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_receive">WskReceive</a> function for the socket.


### -field WskDisconnect

A pointer to the WSK subsystem's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_disconnect">WskDisconnect</a> function for the
     socket.


### -field WskRelease

A pointer to the WSK subsystem's 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff571144(v=vs.85)">WskRelease</a> function for the socket.


### -field WskGetLocalAddress

A pointer to the WSK subsystem's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_get_local_address">WskGetLocalAddress</a> function for the
     socket.


### -field WskGetRemoteAddress

A pointer to the WSK subsystem's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_get_remote_address">WskGetRemoteAddress</a> function for the
     socket.


### -field WskConnectEx

A pointer to the WSK subsystem's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_connect_ex">WskConnectEx</a> function for the
     socket.

### -field WskSendEx

This member is reserved for system use.

### -field WskReceiveEx

This member is reserved for system use.

## -remarks


The member list of the WSK_PROVIDER_STREAM_DISPATCH structure includes an unnamed 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_basic_dispatch">
    WSK_PROVIDER_BASIC_DISPATCH</a> structure. The compiler that is included with the WDK supports a
    Microsoft-specific extension to the C language that allows unnamed structures within structure
    declarations. The result is that the structure members of the WSK_PROVIDER_BASIC_DISPATCH structure are
    included in the WSK_PROVIDER_STREAM_DISPATCH structure as if they were native members of the
    WSK_PROVIDER_STREAM_DISPATCH structure.

A WSK application receives a pointer to a WSK_PROVIDER_STREAM_DISPATCH structure when the WSK
    application calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket">WskSocket</a> function to create a stream socket.
    The pointer is contained in the 
    <b>Dispatch</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a> structure that is received from the
    WSK subsystem.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_client_stream_dispatch">WSK_CLIENT_STREAM_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_basic_dispatch">
    WSK_PROVIDER_BASIC_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket">WskSocket</a>
 

 

