---
UID: NF:netioddk.NmrClientDetachProviderComplete
title: NmrClientDetachProviderComplete function (netioddk.h)
description: The NmrClientDetachProviderComplete function notifies the NMR that a client module has completed detaching from a provider module.
old-location: netvista\nmrclientdetachprovidercomplete.htm
tech.root: netvista
ms.assetid: e54864de-9558-44b1-9c5a-0f2ecc6516b1
ms.date: 05/02/2018
keywords: ["NmrClientDetachProviderComplete function"]
ms.keywords: NmrClientDetachProviderComplete, NmrClientDetachProviderComplete function [Network Drivers Starting with Windows Vista], netioddk/NmrClientDetachProviderComplete, netvista.nmrclientdetachprovidercomplete, nmrref_7fb0e7ef-62a3-4dc4-a0e2-b38005056317.xml
f1_keywords:
 - "netioddk/NmrClientDetachProviderComplete"
 - "NmrClientDetachProviderComplete"
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
- netio.lib
- netio.dll
api_name:
- NmrClientDetachProviderComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NmrClientDetachProviderComplete function


## -description


The 
  <b>NmrClientDetachProviderComplete</b> function notifies the NMR that a client module has completed
  detaching from a provider module.


## -parameters




### -param NmrBindingHandle [in]

A handle used by the NMR to represent the binding between the client module and the provider
     module. The NMR passes this handle to the client module when it calls the client module's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_client_attach_provider_fn">ClientAttachProvider</a> callback
     function.


## -remarks



A client module calls the 
    <b>NmrClientDetachProviderComplete</b> function when it asynchronously completes detaching from a provider
    module after returning STATUS_PENDING from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_client_detach_provider_fn">ClientDetachProvider</a> callback
    function.

A client module should not call the 
    <b>NmrClientDetachProviderComplete</b> function if it returns STATUS_SUCCESS from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_client_detach_provider_fn">ClientDetachProvider</a> callback
    function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_client_attach_provider_fn">ClientAttachProvider</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_client_detach_provider_fn">ClientDetachProvider</a>
 

 

