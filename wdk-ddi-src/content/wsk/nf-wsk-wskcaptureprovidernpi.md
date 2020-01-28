---
UID: NF:wsk.WskCaptureProviderNPI
title: WskCaptureProviderNPI function (wsk.h)
description: The WskCaptureProviderNPI function captures a provider Network Programming Interface (NPI) when it becomes available from the WSK subsystem.
old-location: netvista\wskcaptureprovidernpi.htm
tech.root: netvista
ms.assetid: b5c6667e-33b4-4482-8817-c01d9d314c3a
ms.date: 05/02/2018
ms.keywords: WskCaptureProviderNPI, WskCaptureProviderNPI function [Network Drivers Starting with Windows Vista], netvista.wskcaptureprovidernpi, wsk/WskCaptureProviderNPI, wskref_571be642-7c1c-471d-bf35-73bd6b271cbe.xml
f1_keywords:
 - "wsk/WskCaptureProviderNPI"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Netio.lib
- Netio.dll
api_name:
- WskCaptureProviderNPI
product:
- Windows
targetos: Windows
req.typenames: 
---

# WskCaptureProviderNPI function


## -description


The 
  <b>WskCaptureProviderNPI</b> function captures a provider 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">Network Programming Interface
  (NPI)</a> when it becomes available from the WSK subsystem.


## -parameters




### -param WskRegistration [in]

A pointer to the memory location initialized by 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nf-wsk-wskregister">WskRegister</a> that identifies a WSK
     application's registration instance. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_registration">WSK_REGISTRATION</a>.


### -param WaitTimeout [in]

The time, in milliseconds, that the 
     <b>WskCaptureProviderNPI</b> function can wait until the WSK provider NPI becomes available. Alternately,
     the following can be specified:
     





#### WSK_NO_WAIT

Return from this function immediately if the provider NPI is not available.



#### WSK_INFINITE_WAIT

Wait until the provider NPI is available from the WSK subsystem.

For more information about how this parameter is used, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/registering-a-winsock-kernel-application">Registering a Winsock
     Kernel Application</a>.


### -param WskProviderNpi [out]

A pointer to the NPI returned by the WSK provider. This 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_npi">WSK_PROVIDER_NPI</a> structure contains a
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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nf-wsk-wskreleaseprovidernpi">WskReleaseProviderNPI</a> call that uses
    the same 
    <i>WskRegistration</i> parameter that was passed to 
    <b>WskCaptureProviderNPI</b>.

<b>WskCaptureProviderNPI</b> can be called after a call is made to 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nf-wsk-wskderegister">WskDeregister</a> only if the 
    <i>WskRegistration</i> block is not freed or overwritten. After 
    <b>WskDeregister</b> is called, any further calls to 
    <b>WskCaptureProviderNPI</b> will fail with status code STATUS_DEVICE_NOT_READY, and, unless the provider
    NPI becomes available concurrently, any existing 
    <b>WskCaptureProviderNPI</b> calls that are blocked in other threads waiting for the WSK provider NPI to
    become available will also return immediately with status code STATUS_DEVICE_NOT_READY.

For more information about attaching a WSK application to the WSK subsystem, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/registering-a-winsock-kernel-application">Registering a Winsock Kernel
    Application</a>.

Callers of the 
    <b>WskCaptureProviderNPI</b> function must be running at IRQL = PASSIVE_LEVEL if 
    <i>WaitTimeout</i> is not set to WSK_NO_WAIT; otherwise, callers must be running at IRQL <=
    DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nf-wsk-wskderegister">WskDeregister</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nf-wsk-wskregister">WskRegister</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nf-wsk-wskreleaseprovidernpi">WskReleaseProviderNPI</a>
 

 

