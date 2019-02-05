---
UID: NS:wsk._WSK_CLIENT_DISPATCH
title: _WSK_CLIENT_DISPATCH (wsk.h)
description: The WSK_CLIENT_DISPATCH structure specifies a WSK application's dispatch table of event callback functions for events that are not specific to a particular socket.
old-location: netvista\wsk_client_dispatch.htm
tech.root: netvista
ms.assetid: 6a6116b0-2070-4b46-8359-3c84529cd1c5
ms.date: 05/02/2018
ms.keywords: "*PWSK_CLIENT_DISPATCH, PWSK_CLIENT_DISPATCH, PWSK_CLIENT_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], WSK_CLIENT_DISPATCH, WSK_CLIENT_DISPATCH structure [Network Drivers Starting with Windows Vista], _WSK_CLIENT_DISPATCH, netvista.wsk_client_dispatch, wsk/PWSK_CLIENT_DISPATCH, wsk/WSK_CLIENT_DISPATCH, wskref_59bad29c-be6f-4a0d-8bf6-7112cd2c8855.xml"
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
-	WSK_CLIENT_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: WSK_CLIENT_DISPATCH, *PWSK_CLIENT_DISPATCH
---

# _WSK_CLIENT_DISPATCH structure


## -description


The WSK_CLIENT_DISPATCH structure specifies a WSK application's dispatch table of event callback
  functions for events that are not specific to a particular socket.


## -struct-fields




### -field Version

The version of the WSK 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">Network Programming Interface
     (NPI)</a> that the WSK application would like to use.


### -field Reserved

Reserved for system use. WSK applications must set this member to zero.


### -field WskClientEvent

A pointer to the WSK application's 
     <a href="https://msdn.microsoft.com/5511f540-4448-4cbe-849a-b1712453fae1">WskClientEvent</a> event callback function. If
     a WSK application does not implement a 
     <i>WskClientEvent</i> event callback function, this member must be set to <b>NULL</b>.


## -remarks



When a WSK application calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571143">WskRegister</a> function, it provides a pointer to
    an initialized WSK_CLIENT_DISPATCH structure by means of the 
    <b>Dispatch</b> member of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571163">WSK_CLIENT_NPI</a> structure pointed to by the 
    <i>WskClientNpi</i> parameter.

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
For more information about attaching a WSK application to the WSK subsystem, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/registering-a-winsock-kernel-application">Registering a Winsock Kernel
    Application</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571163">WSK_CLIENT_NPI</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571175">WSK_PROVIDER_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571177">WSK_PROVIDER_NPI</a>



<a href="https://msdn.microsoft.com/5511f540-4448-4cbe-849a-b1712453fae1">WskClientEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571143">WskRegister</a>
 

 

