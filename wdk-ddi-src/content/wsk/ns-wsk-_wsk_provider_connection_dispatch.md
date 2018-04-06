---
UID: NS:wsk._WSK_PROVIDER_CONNECTION_DISPATCH
title: "_WSK_PROVIDER_CONNECTION_DISPATCH"
author: windows-driver-content
description: The WSK_PROVIDER_CONNECTION_DISPATCH structure specifies the WSK subsystem's table of functions for a connection-oriented socket.
old-location: netvista\wsk_provider_connection_dispatch.htm
old-project: netvista
ms.assetid: 70a86809-07f2-4723-9e50-4dbdd31ff900
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWSK_PROVIDER_CONNECTION_DISPATCH, PWSK_PROVIDER_CONNECTION_DISPATCH, PWSK_PROVIDER_CONNECTION_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], WSK_PROVIDER_CONNECTION_DISPATCH, WSK_PROVIDER_CONNECTION_DISPATCH structure [Network Drivers Starting with Windows Vista], _WSK_PROVIDER_CONNECTION_DISPATCH, netvista.wsk_provider_connection_dispatch, wsk/PWSK_PROVIDER_CONNECTION_DISPATCH, wsk/WSK_PROVIDER_CONNECTION_DISPATCH, wskref_b6ef1db8-e10d-44bd-a3df-9dee672b2b9e.xml"
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
-	WSK_PROVIDER_CONNECTION_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: WSK_PROVIDER_CONNECTION_DISPATCH, *PWSK_PROVIDER_CONNECTION_DISPATCH
req.product: Windows 10 or later.
---

# _WSK_PROVIDER_CONNECTION_DISPATCH structure


## -description


The WSK_PROVIDER_CONNECTION_DISPATCH structure specifies the WSK subsystem's table of functions for a
  connection-oriented socket.


## -struct-fields




### -field Basic

The members of the 
     <a href="https://msdn.microsoft.com/15cd5336-fe29-4a59-8071-04c802552a5a">
     WSK_PROVIDER_BASIC_DISPATCH</a> structure are included as members of the 
     <b>WSK_PROVIDER_CONNECTION_DISPATCH</b> structure.


### -field WskBind

A pointer to the WSK subsystem's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571121">WskBind</a> function for the socket.


### -field WskConnect

A pointer to the WSK subsystem's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571125">WskConnect</a> function for the socket.


### -field WskGetLocalAddress

A pointer to the WSK subsystem's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571133">WskGetLocalAddress</a> function for the
     socket.


### -field WskGetRemoteAddress

A pointer to the WSK subsystem's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571135">WskGetRemoteAddress</a> function for the
     socket.


### -field WskSend

A pointer to the WSK subsystem's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571146">WskSend</a> function for the socket.


### -field WskReceive

A pointer to the WSK subsystem's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571139">WskReceive</a> function for the socket.


### -field WskDisconnect

A pointer to the WSK subsystem's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571129">WskDisconnect</a> function for the
     socket.


### -field WskRelease

A pointer to the WSK subsystem's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571144">WskRelease</a> function for the socket.


### -field WskConnectEx

A pointer to the WSK subsystem's 
     <a href="https://msdn.microsoft.com/1BC518E9-747C-4406-8A2A-40A3BCB0A3AA">WskConnectEx</a> function for the
     socket.

### -field WskSendEx

This member is reserved for system use.

### -field WskReceiveEx

This member is reserved for system use.

## -remarks



The member list of the WSK_PROVIDER_CONNECTION_DISPATCH structure includes an unnamed 
    <a href="https://msdn.microsoft.com/15cd5336-fe29-4a59-8071-04c802552a5a">
    WSK_PROVIDER_BASIC_DISPATCH</a> structure. The compiler that is included with the WDK supports a
    Microsoft-specific extension to the C language that allows unnamed structures within structure
    declarations. The result is that the structure members of the WSK_PROVIDER_BASIC_DISPATCH structure are
    included in the WSK_PROVIDER_CONNECTION_DISPATCH structure as if they were native members of the
    WSK_PROVIDER_CONNECTION_DISPATCH structure.

A WSK application receives a pointer to a WSK_PROVIDER_CONNECTION_DISPATCH structure in one of the
    following ways:

<ul>
<li>
The WSK application calls the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a> function to create a
      connection-oriented socket.

</li>
<li>
The WSK application calls the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff571150">WskSocketConnect</a> function to create,
      bind, and connect a connection-oriented socket.

</li>
<li>
The WSK application calls the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff571109">WskAccept</a> function to accept an incoming
      connection-oriented socket on a listening socket.

</li>
<li>
The WSK subsystem calls the WSK application's 
      <a href="https://msdn.microsoft.com/672440f0-810a-4e68-82a5-d038770898c5">WskAcceptEvent</a> event callback function to
      notify the WSK application that an incoming connection-oriented socket has been accepted on a listening
      socket.

</li>
</ul>
The pointer to the WSK_PROVIDER_CONNECTION_DISPATCH structure is contained in the 
    <b>Dispatch</b> member of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a> structure that is received from the
    WSK subsystem.




## -see-also




<a href="https://msdn.microsoft.com/960eee8a-2950-4baf-b32d-be13b3d65951">
   WSK_CLIENT_CONNECTION_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571171">WSK_PROVIDER_BASIC_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571109">WskAccept</a>



<a href="https://msdn.microsoft.com/672440f0-810a-4e68-82a5-d038770898c5">WskAcceptEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571121">WskBind</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571124">WskCloseSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571125">WskConnect</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571127">WskControlSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571129">WskDisconnect</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571133">WskGetLocalAddress</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571135">WskGetRemoteAddress</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571139">WskReceive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571144">WskRelease</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571146">WskSend</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571150">WskSocketConnect</a>
 

 

