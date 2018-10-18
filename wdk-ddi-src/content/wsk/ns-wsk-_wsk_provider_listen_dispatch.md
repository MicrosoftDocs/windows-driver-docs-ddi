---
UID: NS:wsk._WSK_PROVIDER_LISTEN_DISPATCH
title: "_WSK_PROVIDER_LISTEN_DISPATCH"
author: windows-driver-content
description: The WSK_PROVIDER_LISTEN_DISPATCH structure specifies the WSK subsystem's table of functions for a listening socket.
old-location: netvista\wsk_provider_listen_dispatch.htm
tech.root: netvista
ms.assetid: 56df7cb9-9ae7-4249-9583-a9259e604238
ms.date: 5/2/2018
ms.keywords: "*PWSK_PROVIDER_LISTEN_DISPATCH, PWSK_PROVIDER_LISTEN_DISPATCH, PWSK_PROVIDER_LISTEN_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], WSK_PROVIDER_LISTEN_DISPATCH, WSK_PROVIDER_LISTEN_DISPATCH structure [Network Drivers Starting with Windows Vista], _WSK_PROVIDER_LISTEN_DISPATCH, netvista.wsk_provider_listen_dispatch, wsk/PWSK_PROVIDER_LISTEN_DISPATCH, wsk/WSK_PROVIDER_LISTEN_DISPATCH, wskref_f2c1b28d-48f5-4667-bb4e-8dd1d5f25916.xml"
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
-	WSK_PROVIDER_LISTEN_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: WSK_PROVIDER_LISTEN_DISPATCH, *PWSK_PROVIDER_LISTEN_DISPATCH
---

# _WSK_PROVIDER_LISTEN_DISPATCH structure


## -description


The WSK_PROVIDER_LISTEN_DISPATCH structure specifies the WSK subsystem's table of functions for a
  listening socket.


## -struct-fields




### -field Basic

The members of the 
     <a href="https://msdn.microsoft.com/15cd5336-fe29-4a59-8071-04c802552a5a">
     WSK_PROVIDER_BASIC_DISPATCH</a> structure are included as members of the WSK_PROVIDER_LISTEN_DISPATCH
     structure.


### -field WskBind

A pointer to the WSK subsystem's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571121">WskBind</a> function for the socket.


### -field WskAccept

A pointer to the WSK subsystem's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571109">WskAccept</a> function for the socket.


### -field WskInspectComplete

A pointer to the WSK subsystem's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571136">WskInspectComplete</a> function for the
     socket.


### -field WskGetLocalAddress

A pointer to the WSK subsystem's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571133">WskGetLocalAddress</a> function for the
     socket.


## -remarks



The member list of the WSK_PROVIDER_LISTEN_DISPATCH structure includes an unnamed 
    <a href="https://msdn.microsoft.com/15cd5336-fe29-4a59-8071-04c802552a5a">
    WSK_PROVIDER_BASIC_DISPATCH</a> structure. The compiler that is included with the WDK supports a
    Microsoft-specific extension to the C language that allows unnamed structures within structure
    declarations. The result is that the structure members of the WSK_PROVIDER_BASIC_DISPATCH structure are
    included in the WSK_PROVIDER_LISTEN_DISPATCH structure as if they were native members of the
    WSK_PROVIDER_LISTEN_DISPATCH structure.

A WSK application receives a pointer to a WSK_PROVIDER_LISTEN_DISPATCH structure when the WSK
    application calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a> function to create a listening socket.
    The pointer is contained in the 
    <b>Dispatch</b> member of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a> structure that is received from the
    WSK subsystem.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571162">WSK_CLIENT_LISTEN_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571171">WSK_PROVIDER_BASIC_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571109">WskAccept</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571121">WskBind</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571124">WskCloseSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571127">WskControlSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571136">WskInspectComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a>
 

 

