---
UID: NS:wsk._WSK_EXTENSION_CONTROL_OUT
title: "_WSK_EXTENSION_CONTROL_OUT"
author: windows-driver-content
description: The WSK_EXTENSION_CONTROL_OUT structure specifies the WSK subsystem's implementation of an extension interface for a socket.
old-location: netvista\wsk_extension_control_out.htm
old-project: netvista
ms.assetid: aec44058-13ad-4093-91b1-e5dca6f2e295
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PWSK_EXTENSION_CONTROL_OUT, PWSK_EXTENSION_CONTROL_OUT, PWSK_EXTENSION_CONTROL_OUT structure pointer [Network Drivers Starting with Windows Vista], WSK_EXTENSION_CONTROL_OUT, WSK_EXTENSION_CONTROL_OUT structure [Network Drivers Starting with Windows Vista], _WSK_EXTENSION_CONTROL_OUT, netvista.wsk_extension_control_out, wsk/PWSK_EXTENSION_CONTROL_OUT, wsk/WSK_EXTENSION_CONTROL_OUT, wskref_fd819b16-7a6d-4206-b29e-d376e84c8e4d.xml"
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
-	WSK_EXTENSION_CONTROL_OUT
product: Windows
targetos: Windows
req.typenames: WSK_EXTENSION_CONTROL_OUT, *PWSK_EXTENSION_CONTROL_OUT
req.product: Windows 10 or later.
---

# _WSK_EXTENSION_CONTROL_OUT structure


## -description


The WSK_EXTENSION_CONTROL_OUT structure specifies the WSK subsystem's implementation of an extension
  interface for a socket.


## -syntax


````
typedef struct _WSK_EXTENSION_CONTROL_OUT {
  PVOID      ProviderContext;
  const VOID *ProviderDispatch;
} WSK_EXTENSION_CONTROL_OUT, *PWSK_EXTENSION_CONTROL_OUT;
````


## -struct-fields




### -field ProviderContext

A pointer to a WSK subsystem-supplied context for the registration of the extension interface on a
     socket. The WSK subsystem uses this context to track the state of the extension interface registration
     for the socket. The contents of the WSK subsystem's registration context are opaque to the WSK
     application. The WSK application passes this pointer to the WSK subsystem whenever it calls any of the
     socket's extension interface functions that require the WSK subsystem's registration context.


### -field ProviderDispatch

A pointer to a structure that contains the WSK subsystem's dispatch table of functions for the
     extension interface. The contents of the structure are specific to the extension interface.


## -remarks



The WSK subsystem fills in the contents of the WSK_EXTENSION_CONTROL_OUT structure when a WSK
    application registers an extension interface. For more information about registering an extension
    interface, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/registering-an-extension-interface">Registering an Extension
    Interface</a>.




## -see-also

<a href="..\wsk\nc-wsk-pfn_wsk_control_socket.md">WskControlSocket</a>



<a href="..\wsk\ns-wsk-_wsk_extension_control_in.md">WSK_EXTENSION_CONTROL_IN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570819">SIO_WSK_REGISTER_EXTENSION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_EXTENSION_CONTROL_OUT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

