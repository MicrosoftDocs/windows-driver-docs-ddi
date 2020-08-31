---
UID: NF:netioddk.NmrProviderDetachClientComplete
title: NmrProviderDetachClientComplete function (netioddk.h)
description: The NmrProviderDetachClientComplete function notifies the NMR that a provider module has completed detaching from a client module.
old-location: netvista\nmrproviderdetachclientcomplete.htm
tech.root: netvista
ms.assetid: a52b3cfc-d6bd-4569-8b09-36dce65d017f
ms.date: 05/02/2018
keywords: ["NmrProviderDetachClientComplete function"]
ms.keywords: NmrProviderDetachClientComplete, NmrProviderDetachClientComplete function [Network Drivers Starting with Windows Vista], netioddk/NmrProviderDetachClientComplete, netvista.nmrproviderdetachclientcomplete, nmrref_c86f4d4f-b54f-4e31-b683-f692ff7ed1ba.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NmrProviderDetachClientComplete
 - netioddk/NmrProviderDetachClientComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - netio.lib
 - netio.dll
api_name:
 - NmrProviderDetachClientComplete
---

# NmrProviderDetachClientComplete function


## -description

The 
  <b>NmrProviderDetachClientComplete</b> function notifies the NMR that a provider module has completed
  detaching from a client module.

## -parameters

### -param NmrBindingHandle 

[in]
A handle used by the NMR to represent the binding between the client module and the provider
     module. The NMR passes this handle to the provider module when it calls the provider module's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_provider_attach_client_fn">ProviderAttachClient</a> callback
     function.

## -remarks

A provider module calls the 
    <b>NmrProviderDetachClientComplete</b> function when it asynchronously completes detaching from a client
    module after returning STATUS_PENDING from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_provider_detach_client_fn">ProviderDetachClient</a> callback
    function.

A provider module should not call the 
    <b>NmrProviderDetachClientComplete</b> function if it returns STATUS_SUCCESS from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_provider_detach_client_fn">ProviderDetachClient</a> callback
    function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_provider_attach_client_fn">ProviderAttachClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_provider_detach_client_fn">ProviderDetachClient</a>

