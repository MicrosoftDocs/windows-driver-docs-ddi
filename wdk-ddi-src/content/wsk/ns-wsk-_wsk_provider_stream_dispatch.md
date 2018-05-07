---
UID: NS:wsk._WSK_PROVIDER_STREAM_DISPATCH
title: "_WSK_PROVIDER_STREAM_DISPATCH"
author: windows-driver-content
description: The WSK_PROVIDER_STREAM_DISPATCH structure specifies the WSK subsystem's table of functions for a stream socket.
old-location: netvista\wsk_provider_stream_dispatch.htm
old-project: netvista
ms.assetid: A10B901E-9987-40E9-976B-4CD9455E0AEE
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PWSK_PROVIDER_STREAM_DISPATCH, PWSK_PROVIDER_STREAM_DISPATCH, PWSK_PROVIDER_STREAM_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], WSK_PROVIDER_STREAM_DISPATCH, WSK_PROVIDER_STREAM_DISPATCH structure [Network Drivers Starting with Windows Vista], _WSK_PROVIDER_STREAM_DISPATCH, netvista.wsk_provider_stream_dispatch, wsk/PWSK_PROVIDER_STREAM_DISPATCH, wsk/WSK_PROVIDER_STREAM_DISPATCH"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wsk.h
api_name:
-	WSK_PROVIDER_STREAM_DISPATCH
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
     <a href="https://msdn.microsoft.com/15cd5336-fe29-4a59-8071-04c802552a5a">
     WSK_PROVIDER_BASIC_DISPATCH</a> structure are included as members of the WSK_PROVIDER_STREAM_DISPATCH
     structure.


### -field WskBind

A pointer to the WSK subsystem's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571121">WskBind</a> function for the socket.


### -field WskAccept

A pointer to the WSK subsystem's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571109">WskAccept</a> function for the socket.


### -field WskConnect

A pointer to the WSK subsystem's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571125">WskConnect</a> function for the socket.


### -field WskListen

A pointer to the WSK subsystem's 
     <a href="https://msdn.microsoft.com/854C2DA1-1763-4354-8B9D-9AE0C60D8F31">WskListen</a> function for the socket.


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


### -field WskGetLocalAddress

A pointer to the WSK subsystem's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571133">WskGetLocalAddress</a> function for the
     socket.


### -field WskGetRemoteAddress

A pointer to the WSK subsystem's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571135">WskGetRemoteAddress</a> function for the
     socket.


### -field WskConnectEx

A pointer to the WSK subsystem's 
     <a href="https://msdn.microsoft.com/1BC518E9-747C-4406-8A2A-40A3BCB0A3AA">WskConnectEx</a> function for the
     socket.

### -field WskSendEx

This member is reserved for system use.

### -field WskReceiveEx

This member is reserved for system use.

## -remarks


The member list of the WSK_PROVIDER_STREAM_DISPATCH structure includes an unnamed 
    <a href="https://msdn.microsoft.com/15cd5336-fe29-4a59-8071-04c802552a5a">
    WSK_PROVIDER_BASIC_DISPATCH</a> structure. The compiler that is included with the WDK supports a
    Microsoft-specific extension to the C language that allows unnamed structures within structure
    declarations. The result is that the structure members of the WSK_PROVIDER_BASIC_DISPATCH structure are
    included in the WSK_PROVIDER_STREAM_DISPATCH structure as if they were native members of the
    WSK_PROVIDER_STREAM_DISPATCH structure.

A WSK application receives a pointer to a WSK_PROVIDER_STREAM_DISPATCH structure when the WSK
    application calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a> function to create a stream socket.
    The pointer is contained in the 
    <b>Dispatch</b> member of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a> structure that is received from the
    WSK subsystem.




## -see-also




<a href="https://msdn.microsoft.com/7E682868-1D39-4677-A4EC-E7C9F841EC82">WSK_CLIENT_STREAM_DISPATCH</a>



<a href="https://msdn.microsoft.com/15cd5336-fe29-4a59-8071-04c802552a5a">
    WSK_PROVIDER_BASIC_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a>
 

 

