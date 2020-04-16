---
UID: NF:netioddk.NmrDeregisterClient
title: NmrDeregisterClient function (netioddk.h)
description: The NmrDeregisterClient function deregisters a client module from the NMR.
old-location: netvista\nmrderegisterclient.htm
tech.root: netvista
ms.assetid: 64fff189-392e-42c3-8d9a-0d6daa07d2f7
ms.date: 05/02/2018
keywords: ["NmrDeregisterClient function"]
ms.keywords: NmrDeregisterClient, NmrDeregisterClient function [Network Drivers Starting with Windows Vista], netioddk/NmrDeregisterClient, netvista.nmrderegisterclient, nmrref_db73a389-7569-4d1d-9f96-01d4a28cf73e.xml
f1_keywords:
 - "netioddk/NmrDeregisterClient"
req.header: netioddk.h
req.include-header: Wsk.h
req.target-type: Desktop
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Netio.lib
- Netio.dll
api_name:
- NmrDeregisterClient
product:
- Windows
targetos: Windows
req.typenames: 
---

# NmrDeregisterClient function


## -description


The 
  <b>NmrDeregisterClient</b> function deregisters a client module from the NMR.


## -parameters




### -param NmrClientHandle [in]

A handle used by the NMR to represent the registration of the client module. The NMR returns this
     handle to the client module when the client module calls the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nf-netioddk-nmrregisterclient">NmrRegisterClient</a> function.


## -returns



The 
     <b>NmrDeregisterClient</b> function returns one of the following NTSTATUS codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The NMR initiated the deregistration of the client module. The client module must call the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nf-netioddk-nmrwaitforclientderegistercomplete">
       NmrWaitForClientDeregisterComplete</a> function to wait until the deregistration is complete before
       the client module can be unloaded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>
 




## -remarks



When a client module calls the 
    <b>NmrDeregisterClient</b> function, the NMR calls the client module's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_client_detach_provider_fn">ClientDetachProvider</a> callback
    function and the provider module's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_provider_detach_client_fn">ProviderDetachClient</a> callback
    function for each of the bindings between the client module and a provider module. The deregistration of
    the client module from the NMR is complete after the client module has successfully detached from all the
    provider modules to which it is attached and all of those provider modules have successfully detached
    from the client module.

A client module typically calls the 
    <b>NmrDeregisterClient</b> function from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_unload">Unload</a> function to detach itself from all of the
    provider modules to which it is attached before the client module is unloaded from the system. After
    calling the 
    <b>NmrDeregisterClient</b> function, a client module must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nf-netioddk-nmrwaitforclientderegistercomplete">
    NmrWaitForClientDeregisterComplete</a> function to wait for the deregistration to complete before the
    client module can be unloaded. A client module must not return from a call to its 
    <b>Unload</b> function until after deregistration is
    complete.


<div class="alert"><b>Note</b>  If a client module uses the Windows Driver Framework, it will typically call the 
     <b>NmrDeregisterClient</b> function from its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_unload">EvtDriverUnload</a> event callback function. In
     this situation, the client module must not return from a call to its 
     <i>EvtDriverUnload</i> function until after
     deregistration is complete.</div>
<div> </div>





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_client_detach_provider_fn">ClientDetachProvider</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_unload">EvtDriverUnload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nf-netioddk-nmrregisterclient">NmrRegisterClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nf-netioddk-nmrwaitforclientderegistercomplete">
   NmrWaitForClientDeregisterComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_provider_detach_client_fn">ProviderDetachClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_unload">Unload</a>
 

 

