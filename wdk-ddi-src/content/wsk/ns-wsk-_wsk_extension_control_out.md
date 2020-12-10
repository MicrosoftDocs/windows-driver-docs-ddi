---
UID: NS:wsk._WSK_EXTENSION_CONTROL_OUT
title: _WSK_EXTENSION_CONTROL_OUT (wsk.h)
description: The WSK_EXTENSION_CONTROL_OUT structure specifies the WSK subsystem's implementation of an extension interface for a socket.
old-location: netvista\wsk_extension_control_out.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WSK_EXTENSION_CONTROL_OUT structure"]
ms.keywords: "*PWSK_EXTENSION_CONTROL_OUT, PWSK_EXTENSION_CONTROL_OUT, PWSK_EXTENSION_CONTROL_OUT structure pointer [Network Drivers Starting with Windows Vista], WSK_EXTENSION_CONTROL_OUT, WSK_EXTENSION_CONTROL_OUT structure [Network Drivers Starting with Windows Vista], _WSK_EXTENSION_CONTROL_OUT, netvista.wsk_extension_control_out, wsk/PWSK_EXTENSION_CONTROL_OUT, wsk/WSK_EXTENSION_CONTROL_OUT, wskref_fd819b16-7a6d-4206-b29e-d376e84c8e4d.xml"
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
targetos: Windows
req.typenames: WSK_EXTENSION_CONTROL_OUT, *PWSK_EXTENSION_CONTROL_OUT
f1_keywords:
 - _WSK_EXTENSION_CONTROL_OUT
 - wsk/_WSK_EXTENSION_CONTROL_OUT
 - PWSK_EXTENSION_CONTROL_OUT
 - wsk/PWSK_EXTENSION_CONTROL_OUT
 - WSK_EXTENSION_CONTROL_OUT
 - wsk/WSK_EXTENSION_CONTROL_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wsk.h
api_name:
 - WSK_EXTENSION_CONTROL_OUT
---

# _WSK_EXTENSION_CONTROL_OUT structure


## -description

The WSK_EXTENSION_CONTROL_OUT structure specifies the WSK subsystem's implementation of an extension
  interface for a socket.

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
    <a href="/windows-hardware/drivers/network/registering-an-extension-interface">Registering an Extension
    Interface</a>.

## -see-also

<a href="/windows-hardware/drivers/network/sio-wsk-register-extension">SIO_WSK_REGISTER_EXTENSION</a>



<a href="/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_extension_control_in">WSK_EXTENSION_CONTROL_IN</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_control_socket">WskControlSocket</a>
