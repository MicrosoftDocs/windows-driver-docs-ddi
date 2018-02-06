---
UID: NF:netioddk.NmrDeregisterClient
title: NmrDeregisterClient function
author: windows-driver-content
description: The NmrDeregisterClient function deregisters a client module from the NMR.
old-location: netvista\nmrderegisterclient.htm
old-project: netvista
ms.assetid: 64fff189-392e-42c3-8d9a-0d6daa07d2f7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: nmrref_db73a389-7569-4d1d-9f96-01d4a28cf73e.xml, NmrDeregisterClient, netvista.nmrderegisterclient, NmrDeregisterClient function [Network Drivers Starting with Windows Vista], netioddk/NmrDeregisterClient
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Netio.lib
-	Netio.dll
apiname:
-	NmrDeregisterClient
product: Windows
targetos: Windows
req.typenames: "*PNET_DMA_PROVIDER_CHARACTERISTICS, NET_DMA_PROVIDER_CHARACTERISTICS"
---

# NmrDeregisterClient function


## -description


The 
  <b>NmrDeregisterClient</b> function deregisters a client module from the NMR.


## -syntax


````
NTSTATUS NmrDeregisterClient(
  _In_ HANDLE NmrClientHandle
);
````


## -parameters




### -param NmrClientHandle [in]

A handle used by the NMR to represent the registration of the client module. The NMR returns this
     handle to the client module when the client module calls the 
     <a href="..\netioddk\nf-netioddk-nmrregisterclient.md">NmrRegisterClient</a> function.


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
       <a href="..\netioddk\nf-netioddk-nmrwaitforclientderegistercomplete.md">
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
    <a href="..\netioddk\nc-netioddk-npi_client_detach_provider_fn.md">ClientDetachProvider</a> callback
    function and the provider module's 
    <a href="..\netioddk\nc-netioddk-npi_provider_detach_client_fn.md">ProviderDetachClient</a> callback
    function for each of the bindings between the client module and a provider module. The deregistration of
    the client module from the NMR is complete after the client module has successfully detached from all the
    provider modules to which it is attached and all of those provider modules have successfully detached
    from the client module.

A client module typically calls the 
    <b>NmrDeregisterClient</b> function from its 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a> function to detach itself from all of the
    provider modules to which it is attached before the client module is unloaded from the system. After
    calling the 
    <b>NmrDeregisterClient</b> function, a client module must call the 
    <a href="..\netioddk\nf-netioddk-nmrwaitforclientderegistercomplete.md">
    NmrWaitForClientDeregisterComplete</a> function to wait for the deregistration to complete before the
    client module can be unloaded. A client module must not return from a call to its 
    <b>Unload</b> function until after deregistration is
    complete.


<div class="alert"><b>Note</b>  If a client module uses the Windows Driver Framework, it will typically call the 
     <b>NmrDeregisterClient</b> function from its 
     <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_unload.md">EvtDriverUnload</a> event callback function. In
     this situation, the client module must not return from a call to its 
     <i>EvtDriverUnload</i> function until after
     deregistration is complete.</div>
<div> </div>




## -see-also

<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_unload.md">EvtDriverUnload</a>

<a href="..\netioddk\nf-netioddk-nmrwaitforclientderegistercomplete.md">
   NmrWaitForClientDeregisterComplete</a>

<a href="..\netioddk\nc-netioddk-npi_provider_detach_client_fn.md">ProviderDetachClient</a>

<a href="..\netioddk\nf-netioddk-nmrregisterclient.md">NmrRegisterClient</a>

<a href="..\netioddk\nc-netioddk-npi_client_detach_provider_fn.md">ClientDetachProvider</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NmrDeregisterClient function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

