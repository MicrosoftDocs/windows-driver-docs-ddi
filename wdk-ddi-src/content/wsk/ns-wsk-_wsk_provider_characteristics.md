---
UID: NS:wsk._WSK_PROVIDER_CHARACTERISTICS
title: "_WSK_PROVIDER_CHARACTERISTICS"
author: windows-driver-content
description: The WSK_PROVIDER_CHARACTERISTICS structure specifies the characteristics of the WSK subsystem.
old-location: netvista\wsk_provider_characteristics.htm
old-project: netvista
ms.assetid: 25371620-23bb-4a98-9554-14057742b0ca
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PWSK_PROVIDER_CHARACTERISTICS, ,, A, C, D, E, H, I, K, O, P, PWSK_PROVIDER_CHARACTERISTICS, PWSK_PROVIDER_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], R, S, T, V, W, WSK_PROVIDER_CHARACTERISTICS, WSK_PROVIDER_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], _, _WSK_PROVIDER_CHARACTERISTICS, netvista.wsk_provider_characteristics, wsk/PWSK_PROVIDER_CHARACTERISTICS, wsk/WSK_PROVIDER_CHARACTERISTICS, wskref_f552c7d1-89a7-4cb6-aa7c-5f5ddb906deb.xml"
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
-	WSK_PROVIDER_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: WSK_PROVIDER_CHARACTERISTICS, *PWSK_PROVIDER_CHARACTERISTICS
req.product: Windows 10 or later.
---

# _WSK_PROVIDER_CHARACTERISTICS structure


## -description


The WSK_PROVIDER_CHARACTERISTICS structure specifies the characteristics of the WSK subsystem.


## -syntax


````
typedef struct _WSK_PROVIDER_CHARACTERISTICS {
  USHORT HighestVersion;
  USHORT LowestVersion;
} WSK_PROVIDER_CHARACTERISTICS, *PWSK_PROVIDER_CHARACTERISTICS;
````


## -struct-fields




### -field HighestVersion

The highest version of the WSK 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">Network Programming Interface
     (NPI)</a> that is supported by the WSK subsystem.


### -field LowestVersion

The lowest version of the WSK NPI that is supported by the WSK subsystem.


## -remarks



When a 
    <a href="..\wsk\nf-wsk-wskcaptureprovidernpi.md">WskCaptureProviderNPI</a> call fails
    with status code STATUS_NOINTERFACE, the WSK application can use a call to 
    <a href="..\wsk\nf-wsk-wskqueryprovidercharacteristics.md">
    WskQueryProviderCharacteristics</a> to query the range of WSK NPI versions supported by the WSK
    subsystem. 
    <b>WskQueryProviderCharacteristics</b> returns the version information by means of the
    WSK_PROVIDER_CHARACTERISTICS structure. A WSK application can use this information to determine if the
    WSK subsystem supports a version of the WSK NPI that is compatible with the application.

The major and minor version numbers that are contained within the 
    <b>HighestVersion</b> and 
    <b>LowestVersion</b> members are encoded by using the MAKE_WSK_VERSION macro:

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
    <b>HighestVersion</b> and 
    <b>LowestVersion</b> members by using the WSK_MAJOR_VERSION and WSK_MINOR_VERSION macros:

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
If a WSK application determines that the WSK subsystem supports a version of the WSK NPI that is
    compatible with the application, the application should call 
    <a href="..\wsk\nf-wsk-wskregister.md">WskRegister</a> and, by means of the 
    <b>Dispatch</b> member of the 
    <a href="..\wsk\ns-wsk-_wsk_client_npi.md">WSK_CLIENT_NPI</a> structure pointed to by the 
    <i>WskClientNpi</i> parameter, it should specify the exact version of the WSK NPI that it would like to
    use in the 
    <b>Version</b> member of the 
    <a href="..\wsk\ns-wsk-_wsk_client_dispatch.md">WSK_CLIENT_DISPATCH</a> structure. The WSK
    application should specify the remaining members of the WSK_CLIENT_DISPATCH structure to conform with the
    version of the WSK NPI that is specified in the 
    <b>Version</b> member of the structure.

For more information about attaching a WSK application to the WSK subsystem, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/registering-a-winsock-kernel-application">Registering a Winsock Kernel
    Application</a>.




## -see-also

<a href="..\wsk\nf-wsk-wskcaptureprovidernpi.md">WskCaptureProviderNPI</a>



<a href="..\wsk\ns-wsk-_wsk_client_dispatch.md">WSK_CLIENT_DISPATCH</a>



<a href="..\wsk\nf-wsk-wskregister.md">WskRegister</a>



<a href="..\wsk\nf-wsk-wskqueryprovidercharacteristics.md">
   WskQueryProviderCharacteristics</a>



<a href="..\wsk\ns-wsk-_wsk_client_npi.md">WSK_CLIENT_NPI</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_PROVIDER_CHARACTERISTICS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

