---
UID: NF:wsk.WskCaptureProviderNPI
title: WskCaptureProviderNPI function
author: windows-driver-content
description: The WskCaptureProviderNPI function captures a provider Network Programming Interface (NPI) when it becomes available from the WSK subsystem.
old-location: netvista\wskcaptureprovidernpi.htm
old-project: netvista
ms.assetid: b5c6667e-33b4-4482-8817-c01d9d314c3a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: WskCaptureProviderNPI, WskCaptureProviderNPI function [Network Drivers Starting with Windows Vista], netvista.wskcaptureprovidernpi, wsk/WskCaptureProviderNPI, wskref_571be642-7c1c-471d-bf35-73bd6b271cbe.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
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
req.lib: Netio.lib
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Netio.lib
-	Netio.dll
api_name:
-	WskCaptureProviderNPI
product: Windows
targetos: Windows
req.typenames: WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO
req.product: Windows 10 or later.
---

# WskCaptureProviderNPI function


## -description


The 
  <b>WskCaptureProviderNPI</b> function captures a provider 
  <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">Network Programming Interface
  (NPI)</a> when it becomes available from the WSK subsystem.


## -syntax


````
NTSTATUS WskCaptureProviderNPI(
  _In_  PWSK_REGISTRATION WskRegistration,
  _In_  ULONG             WaitTimeout,
  _Out_ PWSK_PROVIDER_NPI WskProviderNpi
);
````


## -parameters




### -param WskRegistration [in]

A pointer to the memory location initialized by 
     <a href="..\wsk\nf-wsk-wskregister.md">WskRegister</a> that identifies a WSK
     application's registration instance. For more information, see 
     <a href="..\wsk\ns-wsk-_wsk_registration.md">WSK_REGISTRATION</a>.


### -param WaitTimeout [in]

The time, in milliseconds, that the 
     <b>WskCaptureProviderNPI</b> function can wait until the WSK provider NPI becomes available. Alternately,
     the following can be specified:
     





#### WSK_NO_WAIT

Return from this function immediately if the provider NPI is not available.



#### WSK_INFINITE_WAIT

Wait until the provider NPI is available from the WSK subsystem.

For more information about how this parameter is used, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/registering-a-winsock-kernel-application">Registering a Winsock
     Kernel Application</a>.


### -param WskProviderNpi [out]

A pointer to the NPI returned by the WSK provider. This 
     <a href="..\wsk\ns-wsk-_wsk_provider_npi.md">WSK_PROVIDER_NPI</a> structure contains a
     pointer to the WSK provider dispatch table of WSK functions that the WSK application can call.


## -returns



<b>WskCaptureProviderNPI</b> returns one of the following NTSTATUS codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The provider NPI capture completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_NOT_READY</b></dt>
</dl>
</td>
<td width="60%">
The provider NPI was not yet available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The version requested by the WSK client is not supported by the WSK subsystem.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
The provider NPI capture failed.

</td>
</tr>
</table>
 




## -remarks



For each call to 
    <b>WskCaptureProviderNPI</b> that returns a success code, there must be exactly one corresponding 
    <a href="..\wsk\nf-wsk-wskreleaseprovidernpi.md">WskReleaseProviderNPI</a> call that uses
    the same 
    <i>WskRegistration</i> parameter that was passed to 
    <b>WskCaptureProviderNPI</b>.

<b>WskCaptureProviderNPI</b> can be called after a call is made to 
    <a href="..\wsk\nf-wsk-wskderegister.md">WskDeregister</a> only if the 
    <i>WskRegistration</i> block is not freed or overwritten. After 
    <b>WskDeregister</b> is called, any further calls to 
    <b>WskCaptureProviderNPI</b> will fail with status code STATUS_DEVICE_NOT_READY, and, unless the provider
    NPI becomes available concurrently, any existing 
    <b>WskCaptureProviderNPI</b> calls that are blocked in other threads waiting for the WSK provider NPI to
    become available will also return immediately with status code STATUS_DEVICE_NOT_READY.

For more information about attaching a WSK application to the WSK subsystem, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/registering-a-winsock-kernel-application">Registering a Winsock Kernel
    Application</a>.

Callers of the 
    <b>WskCaptureProviderNPI</b> function must be running at IRQL = PASSIVE_LEVEL if 
    <i>WaitTimeout</i> is not set to WSK_NO_WAIT; otherwise, callers must be running at IRQL &lt;=
    DISPATCH_LEVEL.




## -see-also

<a href="..\wsk\nf-wsk-wskreleaseprovidernpi.md">WskReleaseProviderNPI</a>



<a href="..\wsk\nf-wsk-wskregister.md">WskRegister</a>



<a href="..\wsk\nf-wsk-wskderegister.md">WskDeregister</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WskCaptureProviderNPI function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

