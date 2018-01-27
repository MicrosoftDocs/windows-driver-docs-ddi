---
UID: NS:wsk._WSK_PROVIDER_DISPATCH
title: _WSK_PROVIDER_DISPATCH
author: windows-driver-content
description: The WSK_PROVIDER_DISPATCH structure specifies the WSK subsystem's dispatch table of functions that are not specific to a particular socket.
old-location: netvista\wsk_provider_dispatch.htm
old-project: netvista
ms.assetid: 864891dd-7db5-4343-9014-c6a284f1fd7e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WSK_PROVIDER_DISPATCH structure [Network Drivers Starting with Windows Vista], WSK_PROVIDER_DISPATCH, PWSK_PROVIDER_DISPATCH, _WSK_PROVIDER_DISPATCH, *PWSK_PROVIDER_DISPATCH, PWSK_PROVIDER_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], netvista.wsk_provider_dispatch, wskref_3e9340b7-e9e6-46bd-8f28-810354655c6c.xml, wsk/PWSK_PROVIDER_DISPATCH, wsk/WSK_PROVIDER_DISPATCH
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
req.irql: <= DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	wsk.h
apiname: 
-	WSK_PROVIDER_DISPATCH
product: Windows
targetos: Windows
req.typenames: *PWSK_PROVIDER_DISPATCH, WSK_PROVIDER_DISPATCH
req.product: Windows 10 or later.
---

# _WSK_PROVIDER_DISPATCH structure


## -description


The WSK_PROVIDER_DISPATCH structure specifies the WSK subsystem's dispatch table of functions that
  are not specific to a particular socket.


## -syntax


````
typedef struct _WSK_PROVIDER_DISPATCH {
  USHORT                    Version;
  USHORT                    Reserved;
  PFN_WSK_SOCKET            WskSocket;
  PFN_WSK_SOCKET_CONNECT    WskSocketConnect;
  PFN_WSK_CONTROL_CLIENT    WskControlClient;
#if (NTDDI_VERSION >= NTDDI_WIN7)
  PFN_WSK_GET_ADDRESS_INFO  WskGetAddressInfo;
  PFN_WSK_FREE_ADDRESS_INFO WskFreeAddressInfo;
  PFN_WSK_GET_NAME_INFO     WskGetNameInfo;
#endif 
} WSK_PROVIDER_DISPATCH, *PWSK_PROVIDER_DISPATCH;
````


## -struct-fields




### -field Version

The version of the WSK 
     <mshelp:link keywords="netvista.network_programming_interface" tabindex="0">Network Programming Interface
     (NPI)</mshelp:link> that the WSK subsystem will use for its attachment to the WSK application.


### -field Reserved

Reserved for system use.


### -field WskSocket

A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a> function.


### -field WskSocketConnect

A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a> function.


### -field WskControlClient

A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn_wsk_control_client.md">WskControlClient</a> function.


### -field WskGetAddressInfo

A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn_wsk_get_address_info.md">WskGetAddressInfo</a> function.
     

This member is available beginning with Windows 7.


### -field WskFreeAddressInfo

A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn_wsk_free_address_info.md">WskFreeAddressInfo</a> function.
     

This member is available beginning with Windows 7.


### -field WskGetNameInfo

A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn_wsk_get_name_info.md">WskGetNameInfo</a> function.
     

This member is available beginning with Windows 7.


## -remarks


When a WSK application calls the 
    <a href="..\wsk\nf-wsk-wskcaptureprovidernpi.md">WskCaptureProviderNPI</a> function, the
    WSK subsystem returns a pointer to a WSK_PROVIDER_DISPATCH structure by means of the 
    <b>Dispatch</b> member of the 
    <a href="..\wsk\ns-wsk-_wsk_client_npi.md">WSK_CLIENT_NPI</a> structure pointed to by the 
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
</table></span></div>The major and minor version numbers can be extracted from the 
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
</table></span></div>The minor version number that is contained within the 
    <b>Version</b> member of this structure might be a higher minor version number than what was requested by
    the WSK application in the 
    <b>Version</b> member of the 
    <a href="..\wsk\ns-wsk-_wsk_client_dispatch.md">WSK_CLIENT_DISPATCH</a> structure. This
    situation should not cause a problem for the WSK application because higher minor versions of the WSK NPI
    are a strict superset of lower minor versions of the WSK NPI if they have the same major version number.
    The WSK subsystem will specify the remaining members of the WSK_PROVIDER_DISPATCH structure to conform to
    the version of the WSK NPI that is indicated in the 
    <b>Version</b> member of the structure.

For more information about attaching a WSK application to the WSK subsystem, see 
    <mshelp:link keywords="netvista.registering_a_winsock_kernel_application" tabindex="0">Registering a Winsock Kernel
    Application</mshelp:link>.



## -see-also

<a href="..\wsk\nf-wsk-wskcaptureprovidernpi.md">WskCaptureProviderNPI</a>

<a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a>

<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>

<a href="..\wsk\ns-wsk-_wsk_client_dispatch.md">WSK_CLIENT_DISPATCH</a>

<a href="..\wsk\nc-wsk-pfn_wsk_control_client.md">WskControlClient</a>

<a href="..\wsk\ns-wsk-_wsk_client_npi.md">WSK_CLIENT_NPI</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_PROVIDER_DISPATCH structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

