---
UID: NS:wsk._WSK_PROVIDER_DISPATCH
title: _WSK_PROVIDER_DISPATCH (wsk.h)
description: The WSK_PROVIDER_DISPATCH structure specifies the WSK subsystem's dispatch table of functions that are not specific to a particular socket.
old-location: netvista\wsk_provider_dispatch.htm
tech.root: netvista
ms.assetid: 864891dd-7db5-4343-9014-c6a284f1fd7e
ms.date: 05/02/2018
ms.keywords: "*PWSK_PROVIDER_DISPATCH, PWSK_PROVIDER_DISPATCH, PWSK_PROVIDER_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], WSK_PROVIDER_DISPATCH, WSK_PROVIDER_DISPATCH structure [Network Drivers Starting with Windows Vista], _WSK_PROVIDER_DISPATCH, netvista.wsk_provider_dispatch, wsk/PWSK_PROVIDER_DISPATCH, wsk/WSK_PROVIDER_DISPATCH, wskref_3e9340b7-e9e6-46bd-8f28-810354655c6c.xml"
f1_keywords:
 - "wsk/WSK_PROVIDER_DISPATCH"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wsk.h
api_name:
- WSK_PROVIDER_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: WSK_PROVIDER_DISPATCH, *PWSK_PROVIDER_DISPATCH
---

# _WSK_PROVIDER_DISPATCH structure


## -description


The WSK_PROVIDER_DISPATCH structure specifies the WSK subsystem's dispatch table of functions that
  are not specific to a particular socket.


## -struct-fields




### -field Version

The version of the WSK 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">Network Programming Interface
     (NPI)</a> that the WSK subsystem will use for its attachment to the WSK application.


### -field Reserved

Reserved for system use.


### -field WskSocket

A pointer to the WSK subsystem's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket">WskSocket</a> function.


### -field WskSocketConnect

A pointer to the WSK subsystem's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket_connect">WskSocketConnect</a> function.


### -field WskControlClient

A pointer to the WSK subsystem's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_control_client">WskControlClient</a> function.


### -field WskGetAddressInfo

A pointer to the WSK subsystem's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_get_address_info">WskGetAddressInfo</a> function.
     

This member is available beginning with Windows 7.


### -field WskFreeAddressInfo

A pointer to the WSK subsystem's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_free_address_info">WskFreeAddressInfo</a> function.
     

This member is available beginning with Windows 7.


### -field WskGetNameInfo

A pointer to the WSK subsystem's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_get_name_info">WskGetNameInfo</a> function.
     

This member is available beginning with Windows 7.


## -remarks



When a WSK application calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nf-wsk-wskcaptureprovidernpi">WskCaptureProviderNPI</a> function, the
    WSK subsystem returns a pointer to a WSK_PROVIDER_DISPATCH structure by means of the 
    <b>Dispatch</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_client_npi">WSK_CLIENT_NPI</a> structure pointed to by the 
    <i>WskProviderNpi</i> parameter.

The major and minor version numbers that are contained within the 
    <b>Version</b> member are encoded by using the MAKE_WSK_VERSION macro:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>Version = MAKE_WSK_VERSION(Major,Minor);</pre>
</td>
</tr>
</table></span></div>
The major and minor version numbers can be extracted from the 
    <b>Version</b> member by using the WSK_MAJOR_VERSION and WSK_MINOR_VERSION macros:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>Major = WSK_MAJOR_VERSION(Version);
Minor = WSK_MINOR_VERSION(Version);</pre>
</td>
</tr>
</table></span></div>
The minor version number that is contained within the 
    <b>Version</b> member of this structure might be a higher minor version number than what was requested by
    the WSK application in the 
    <b>Version</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_client_dispatch">WSK_CLIENT_DISPATCH</a> structure. This
    situation should not cause a problem for the WSK application because higher minor versions of the WSK NPI
    are a strict superset of lower minor versions of the WSK NPI if they have the same major version number.
    The WSK subsystem will specify the remaining members of the WSK_PROVIDER_DISPATCH structure to conform to
    the version of the WSK NPI that is indicated in the 
    <b>Version</b> member of the structure.

For more information about attaching a WSK application to the WSK subsystem, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/registering-a-winsock-kernel-application">Registering a Winsock Kernel
    Application</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_client_dispatch">WSK_CLIENT_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_client_npi">WSK_CLIENT_NPI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nf-wsk-wskcaptureprovidernpi">WskCaptureProviderNPI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_control_client">WskControlClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket">WskSocket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_socket_connect">WskSocketConnect</a>
 

 

