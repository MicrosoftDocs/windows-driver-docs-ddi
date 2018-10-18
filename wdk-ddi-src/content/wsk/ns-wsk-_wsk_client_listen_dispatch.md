---
UID: NS:wsk._WSK_CLIENT_LISTEN_DISPATCH
title: "_WSK_CLIENT_LISTEN_DISPATCH"
author: windows-driver-content
description: The WSK_CLIENT_LISTEN_DISPATCH structure specifies a WSK application's dispatch table of event callback functions for a listening socket.
old-location: netvista\wsk_client_listen_dispatch.htm
tech.root: netvista
ms.assetid: aaef10f5-2933-4e16-aca6-2277b52fb174
ms.date: 5/2/2018
ms.keywords: "*PWSK_CLIENT_LISTEN_DISPATCH, PWSK_CLIENT_LISTEN_DISPATCH, PWSK_CLIENT_LISTEN_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], WSK_CLIENT_LISTEN_DISPATCH, WSK_CLIENT_LISTEN_DISPATCH structure [Network Drivers Starting with Windows Vista], _WSK_CLIENT_LISTEN_DISPATCH, netvista.wsk_client_listen_dispatch, wsk/PWSK_CLIENT_LISTEN_DISPATCH, wsk/WSK_CLIENT_LISTEN_DISPATCH, wskref_38021620-217a-4a26-b461-f59f87c9579d.xml"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wsk.h
api_name:
-	WSK_CLIENT_LISTEN_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: WSK_CLIENT_LISTEN_DISPATCH, *PWSK_CLIENT_LISTEN_DISPATCH
---

# _WSK_CLIENT_LISTEN_DISPATCH structure


## -description


The WSK_CLIENT_LISTEN_DISPATCH structure specifies a WSK application's dispatch table of event
  callback functions for a listening socket.


## -struct-fields




### -field WskAcceptEvent

A pointer to the WSK application's 
     <a href="https://msdn.microsoft.com/672440f0-810a-4e68-82a5-d038770898c5">WskAcceptEvent</a> event callback function for
     the socket. If the WSK application does not enable the 
     <i>WskAcceptEvent</i> event callback function for the socket, this pointer can be <b>NULL</b>.


### -field WskInspectEvent

A pointer to the WSK application's 
     <a href="https://msdn.microsoft.com/40f184ac-4ef3-485a-a529-71c1f2716427">WskInspectEvent</a> event callback function
     for the socket. If the WSK application does not enable conditional accept mode for the socket, this
     pointer can be <b>NULL</b>.


### -field WskAbortEvent

A pointer to the WSK application's 
     <a href="https://msdn.microsoft.com/50e0ef5d-0577-4b5c-b541-fc78079a953c">WskAbortEvent</a> event callback function for
     the socket. If the WSK application does not enable conditional accept mode for the socket, this pointer
     can be <b>NULL</b>.


## -remarks



A WSK application passes a pointer to a WSK_CLIENT_LISTEN_DISPATCH structure to the WSK subsystem when
    the WSK application calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a> function to create a listening
    socket.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571176">WSK_PROVIDER_LISTEN_DISPATCH</a>



<a href="https://msdn.microsoft.com/50e0ef5d-0577-4b5c-b541-fc78079a953c">WskAbortEvent</a>



<a href="https://msdn.microsoft.com/672440f0-810a-4e68-82a5-d038770898c5">WskAcceptEvent</a>



<a href="https://msdn.microsoft.com/40f184ac-4ef3-485a-a529-71c1f2716427">WskInspectEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a>
 

 

