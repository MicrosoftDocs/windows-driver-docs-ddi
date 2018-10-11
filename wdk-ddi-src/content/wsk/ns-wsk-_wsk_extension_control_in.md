---
UID: NS:wsk._WSK_EXTENSION_CONTROL_IN
title: "_WSK_EXTENSION_CONTROL_IN"
author: windows-driver-content
description: The WSK_EXTENSION_CONTROL_IN structure specifies a WSK application's implementation of an extension interface for a socket.
old-location: netvista\wsk_extension_control_in.htm
tech.root: netvista
ms.assetid: d04f4c24-15a5-490a-aada-af1050f727d4
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: "*PWSK_EXTENSION_CONTROL_IN, PWSK_EXTENSION_CONTROL_IN, PWSK_EXTENSION_CONTROL_IN structure pointer [Network Drivers Starting with Windows Vista], WSK_EXTENSION_CONTROL_IN, WSK_EXTENSION_CONTROL_IN structure [Network Drivers Starting with Windows Vista], _WSK_EXTENSION_CONTROL_IN, netvista.wsk_extension_control_in, wsk/PWSK_EXTENSION_CONTROL_IN, wsk/WSK_EXTENSION_CONTROL_IN, wskref_d922851d-20e4-4ffd-bb3e-e1752b223a1c.xml"
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
-	WSK_EXTENSION_CONTROL_IN
product:
- Windows
targetos: Windows
req.typenames: WSK_EXTENSION_CONTROL_IN, *PWSK_EXTENSION_CONTROL_IN
---

# _WSK_EXTENSION_CONTROL_IN structure


## -description


The WSK_EXTENSION_CONTROL_IN structure specifies a WSK application's implementation of an extension
  interface for a socket.


## -struct-fields




### -field NpiId

A pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">Network Programming Interface
     (NPI)</a> identifier that identifies the extension interface.


### -field ClientContext

A pointer to a WSK application-supplied context for the registration of the extension interface on
     a socket. A WSK application uses this context to track the state of the extension interface registration
     for the socket. The contents of the WSK application's registration context are opaque to the WSK
     subsystem. The WSK subsystem passes this pointer to the WSK application whenever it calls any of the
     socket's extension interface event callback functions that require the WSK application's registration
     context.


### -field ClientDispatch

A pointer to a structure that contains the WSK application's dispatch table of event callback
     functions for the extension interface. The contents of the structure are specific to the extension
     interface.


## -remarks



A WSK application passes a pointer to a WSK_EXTENSION_CONTROL_IN structure to the WSK subsystem when
    registering an extension interface. For more information about registering an extension interface, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/registering-an-extension-interface">Registering an Extension
    Interface</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570819">SIO_WSK_REGISTER_EXTENSION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571168">WSK_EXTENSION_CONTROL_OUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571127">WskControlSocket</a>
 

 

