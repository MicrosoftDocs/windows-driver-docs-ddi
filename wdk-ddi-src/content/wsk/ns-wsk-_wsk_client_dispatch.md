---
UID: NS:wsk._WSK_CLIENT_DISPATCH
title: _WSK_CLIENT_DISPATCH (wsk.h)
description: The WSK_CLIENT_DISPATCH structure specifies a WSK application's dispatch table of event callback functions for events that are not specific to a particular socket.
old-location: netvista\wsk_client_dispatch.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WSK_CLIENT_DISPATCH structure"]
ms.keywords: "*PWSK_CLIENT_DISPATCH, PWSK_CLIENT_DISPATCH, PWSK_CLIENT_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], WSK_CLIENT_DISPATCH, WSK_CLIENT_DISPATCH structure [Network Drivers Starting with Windows Vista], _WSK_CLIENT_DISPATCH, netvista.wsk_client_dispatch, wsk/PWSK_CLIENT_DISPATCH, wsk/WSK_CLIENT_DISPATCH, wskref_59bad29c-be6f-4a0d-8bf6-7112cd2c8855.xml"
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
req.typenames: WSK_CLIENT_DISPATCH, *PWSK_CLIENT_DISPATCH
f1_keywords:
 - _WSK_CLIENT_DISPATCH
 - wsk/_WSK_CLIENT_DISPATCH
 - PWSK_CLIENT_DISPATCH
 - wsk/PWSK_CLIENT_DISPATCH
 - WSK_CLIENT_DISPATCH
 - wsk/WSK_CLIENT_DISPATCH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wsk.h
api_name:
 - WSK_CLIENT_DISPATCH
---

# _WSK_CLIENT_DISPATCH structure


## -description

The WSK_CLIENT_DISPATCH structure specifies a WSK application's dispatch table of event callback
  functions for events that are not specific to a particular socket.

## -struct-fields

### -field Version

The version of the WSK 
     <a href="/windows-hardware/drivers/network/network-programming-interface">Network Programming Interface
     (NPI)</a> that the WSK application would like to use.

### -field Reserved

Reserved for system use. WSK applications must set this member to zero.

### -field WskClientEvent

A pointer to the WSK application's 
     <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_client_event">WskClientEvent</a> event callback function. If
     a WSK application does not implement a 
     <i>WskClientEvent</i> event callback function, this member must be set to <b>NULL</b>.

## -remarks

When a WSK application calls the 
    <a href="/windows-hardware/drivers/ddi/wsk/nf-wsk-wskregister">WskRegister</a> function, it provides a pointer to
    an initialized WSK_CLIENT_DISPATCH structure by means of the 
    <b>Dispatch</b> member of the 
    <a href="/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_client_npi">WSK_CLIENT_NPI</a> structure pointed to by the 
    <i>WskClientNpi</i> parameter.

The major and minor version numbers that are contained within the 
    <b>Version</b> member are encoded by using the MAKE_WSK_VERSION macro:


```
Version = MAKE_WSK_VERSION(Major,Minor);
```

The major and minor version numbers can be extracted from the 
    <b>Version</b> member by using the WSK_MAJOR_VERSION and WSK_MINOR_VERSION macros:


```
Major = WSK_MAJOR_VERSION(Version);
Minor = WSK_MINOR_VERSION(Version);
```

For more information about attaching a WSK application to the WSK subsystem, see 
    <a href="/windows-hardware/drivers/network/registering-a-winsock-kernel-application">Registering a Winsock Kernel
    Application</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_client_npi">WSK_CLIENT_NPI</a>



<a href="/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_dispatch">WSK_PROVIDER_DISPATCH</a>



<a href="/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_npi">WSK_PROVIDER_NPI</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_client_event">WskClientEvent</a>



<a href="/windows-hardware/drivers/ddi/wsk/nf-wsk-wskregister">WskRegister</a>
