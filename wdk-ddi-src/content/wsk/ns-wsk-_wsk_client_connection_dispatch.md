---
UID: NS:wsk._WSK_CLIENT_CONNECTION_DISPATCH
title: "_WSK_CLIENT_CONNECTION_DISPATCH"
author: windows-driver-content
description: The WSK_CLIENT_CONNECTION_DISPATCH structure specifies a WSK application's dispatch table of event callback functions for a connection-oriented socket.
old-location: netvista\wsk_client_connection_dispatch.htm
old-project: netvista
ms.assetid: 960eee8a-2950-4baf-b32d-be13b3d65951
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PWSK_CLIENT_CONNECTION_DISPATCH, PWSK_CLIENT_CONNECTION_DISPATCH, PWSK_CLIENT_CONNECTION_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], WSK_CLIENT_CONNECTION_DISPATCH, WSK_CLIENT_CONNECTION_DISPATCH structure [Network Drivers Starting with Windows Vista], _WSK_CLIENT_CONNECTION_DISPATCH, netvista.wsk_client_connection_dispatch, wsk/PWSK_CLIENT_CONNECTION_DISPATCH, wsk/WSK_CLIENT_CONNECTION_DISPATCH, wskref_2fd26ffb-dab8-4529-9fd0-6043509312c9.xml"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wsk.h
api_name:
-	WSK_CLIENT_CONNECTION_DISPATCH
product: Windows
targetos: Windows
req.typenames: WSK_CLIENT_CONNECTION_DISPATCH, *PWSK_CLIENT_CONNECTION_DISPATCH
---

# _WSK_CLIENT_CONNECTION_DISPATCH structure


## -description


The WSK_CLIENT_CONNECTION_DISPATCH structure specifies a WSK application's dispatch table of event
  callback functions for a connection-oriented socket.


## -struct-fields




### -field WskReceiveEvent

A pointer to the WSK application's 
     <a href="https://msdn.microsoft.com/2a7a7570-ed26-48be-b27b-dc240588ecfc">WskReceiveEvent</a> event callback function
     for the socket. If the WSK application does not enable the 
     <i>WskReceiveEvent</i> event callback function for the socket, this pointer can be <b>NULL</b>.


### -field WskDisconnectEvent

A pointer to the WSK application's 
     <a href="https://msdn.microsoft.com/bf12d7b3-080e-46d9-b276-76d42068e7c6">WskDisconnectEvent</a> event callback
     function for the socket. If the WSK application does not enable the 
     <i>WskDisconnectEvent</i> event callback function for the socket, this pointer can be <b>NULL</b>.


### -field WskSendBacklogEvent

A pointer to the WSK application's 
     <a href="https://msdn.microsoft.com/e944af6f-6753-48b0-b3f6-0709f24e3ff0">WskSendBacklogEvent</a> event callback
     function for the socket. If the WSK application does not enable the 
     <i>WskSendBacklogEvent</i> event callback function for the socket, this pointer can be <b>NULL</b>.


## -remarks



A WSK application passes a pointer to a WSK_CLIENT_CONNECTION_DISPATCH structure to the WSK subsystem
    in one of the following ways:

<ul>
<li>
When calling the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a> function to create a
      connection-oriented socket.

</li>
<li>
When calling the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff571150">WskSocketConnect</a> function to create,
      bind, and connect a connection-oriented socket.

</li>
<li>
When calling the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff571109">WskAccept</a> function to accept an incoming
      connection-oriented socket on a listening socket.

</li>
<li>
As a returned parameter when the WSK subsystem calls the WSK application's 
      <a href="https://msdn.microsoft.com/672440f0-810a-4e68-82a5-d038770898c5">WskAcceptEvent</a> event callback function.
      The WSK subsystem calls a WSK application's 
      <i>WskAcceptEvent</i> event callback function to notify the WSK application that an incoming
      connection-oriented socket has been accepted on a listening socket.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/70a86809-07f2-4723-9e50-4dbdd31ff900">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571109">WskAccept</a>



<a href="https://msdn.microsoft.com/672440f0-810a-4e68-82a5-d038770898c5">WskAcceptEvent</a>



<a href="https://msdn.microsoft.com/bf12d7b3-080e-46d9-b276-76d42068e7c6">WskDisconnectEvent</a>



<a href="https://msdn.microsoft.com/2a7a7570-ed26-48be-b27b-dc240588ecfc">WskReceiveEvent</a>



<a href="https://msdn.microsoft.com/e944af6f-6753-48b0-b3f6-0709f24e3ff0">WskSendBacklogEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571150">WskSocketConnect</a>
 

 

