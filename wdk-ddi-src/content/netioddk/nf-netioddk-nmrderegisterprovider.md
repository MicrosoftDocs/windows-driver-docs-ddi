---
UID: NF:netioddk.NmrDeregisterProvider
title: NmrDeregisterProvider function
author: windows-driver-content
description: The NmrDeregisterProvider function deregisters a provider module from the NMR.
old-location: netvista\nmrderegisterprovider.htm
old-project: netvista
ms.assetid: 889f872a-f4fe-4d7a-b9b6-7fb7335831a5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NmrDeregisterProvider, NmrDeregisterProvider function [Network Drivers Starting with Windows Vista], netioddk/NmrDeregisterProvider, netvista.nmrderegisterprovider, nmrref_581ad526-b42f-4ff3-993c-58558cd281c8.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Netio.lib
-	Netio.dll
api_name:
-	NmrDeregisterProvider
product: Windows
targetos: Windows
req.typenames: NET_DMA_PROVIDER_CHARACTERISTICS, *PNET_DMA_PROVIDER_CHARACTERISTICS
---

# NmrDeregisterProvider function


## -description


The 
  <b>NmrDeregisterProvider</b> function deregisters a provider module from the NMR.


## -syntax


````
NTSTATUS NmrDeregisterProvider(
  _In_ HANDLE NmrProviderHandle
);
````


## -parameters




### -param NmrProviderHandle [in]

A handle used by the NMR to represent the registration of the provider module. The NMR returns
     this handle to the provider module when the provider module calls the 
     <a href="..\netioddk\nf-netioddk-nmrregisterprovider.md">NmrRegisterProvider</a> function.


## -returns



The 
     <b>NmrDeregisterProvider</b> function returns one of the following NTSTATUS codes:

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
The NMR initiated the deregistration of the provider module. The provider module must call the 
       <a href="..\netioddk\nf-netioddk-nmrwaitforproviderderegistercomplete.md">
       NmrWaitForProviderDeregisterComplete</a> function to wait until the deregistration is complete
       before the provider module can be unloaded.

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



When a provider module calls the 
    <b>NmrDeregisterProvider</b> function, the NMR calls the provider module's 
    <a href="..\netioddk\nc-netioddk-npi_provider_detach_client_fn.md">ProviderDetachClient</a> callback
    function and the client module's 
    <a href="..\netioddk\nc-netioddk-npi_client_detach_provider_fn.md">ClientDetachProvider</a> callback
    function for each of the bindings between the provider module and a client module. The deregistration of
    the provider module from the NMR is complete after the provider module has successfully detached from all
    the client modules to which it is attached and all of those client modules have successfully detached
    from the provider module.

A provider module typically calls the 
    <b>NmrDeregisterProvider</b> function from its 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a> function to detach itself from all of the
    client modules to which it is attached before the provider module is unloaded from the system. After
    calling the 
    <b>NmrDeregisterProvider</b> function a provider module must call the 
    <a href="..\netioddk\nf-netioddk-nmrwaitforproviderderegistercomplete.md">
    NmrWaitForProviderDeregisterComplete</a> function to wait for the deregistration to complete before the
    provider module can be unloaded. A provider module must not return from a call to its 
    <i>Unload</i> function until after deregistration is
    complete.


<div class="alert"><b>Note</b>  If a provider module uses the Windows Driver Framework, it will typically call the
     
     <b>NmrDeregisterProvider</b> function from its 
     <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_unload.md">EvtDriverUnload</a> event callback function. In
     this situation, the provider module must not return from a call to its 
     <i>EvtDriverUnload</i> function until after
     deregistration is complete.</div>
<div> </div>





## -see-also

<a href="..\netioddk\nc-netioddk-npi_client_detach_provider_fn.md">ClientDetachProvider</a>



<a href="..\netioddk\nf-netioddk-nmrwaitforproviderderegistercomplete.md">
   NmrWaitForProviderDeregisterComplete</a>



<a href="..\netioddk\nf-netioddk-nmrregisterprovider.md">NmrRegisterProvider</a>



<a href="..\netioddk\nc-netioddk-npi_provider_detach_client_fn.md">ProviderDetachClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a>



<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_unload.md">EvtDriverUnload</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NmrDeregisterProvider function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

