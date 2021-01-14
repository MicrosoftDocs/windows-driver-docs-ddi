---
UID: NC:netioddk.NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN
title: NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN (netioddk.h)
description: A provider module's ProviderCleanupBindingContext callback function performs any necessary cleanup and deallocation of the provider module's binding context after the provider module and a client module have detached from one another.
old-location: netvista\providercleanupbindingcontext.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN callback function"]
ms.keywords: NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN, NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN callback, PNPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN, PNPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN callback function [Network Drivers Starting with Windows Vista], ProviderCleanupBindingContext, ProviderCleanupBindingContext callback function [Network Drivers Starting with Windows Vista], netioddk/ProviderCleanupBindingContext, netvista.providercleanupbindingcontext, nmrref_9723dfb1-96dd-410c-a5cd-1adfb6aa9544.xml
req.header: netioddk.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN
 - netioddk/NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - netioddk.h
api_name:
 - NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN
---

# NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN callback function


## -description

A provider module's 
  <i>ProviderCleanupBindingContext</i> callback function performs any necessary cleanup and deallocation of
  the provider module's binding context after the provider module and a client module have detached from one
  another.

## -parameters

### -param ProviderBindingContext 

[in]
A pointer to the provider module's context for the binding between the provider module and the
     client module from which it has detached. The provider module's 
     <a href="/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_provider_attach_client_fn">ProviderAttachClient</a> callback
     function returns this pointer to the NMR when it attaches to the client module.

## -remarks

The NMR calls a provider module's 
    <i>ProviderCleanupBindingContext</i> callback function after the provider and a client module have
    detached from one another.

A provider module's 
    <i>ProviderCleanupBindingContext</i> callback function should perform any necessary cleanup of the data
    contained within the provider module's binding context structure. It should then free the memory for the
    binding context structure if the provider module dynamically allocated the memory for the structure.

If the provider module does not dynamically allocate the memory for its binding context and no other
    cleanup of its binding context is required, then the provider module does not need to implement a 
    <i>ProviderCleanupBindingContext</i> callback function. If the provider module does not implement a 
    <i>ProviderCleanupBindingContext</i> callback function, then it must set the 
    <i>ProviderCleanupBindingContext</i> member of the 
    <a href="/windows-hardware/drivers/ddi/netioddk/ns-netioddk-_npi_provider_characteristics">
    NPI_PROVIDER_CHARACTERISTICS</a> structure to <b>NULL</b> when it calls the 
    <a href="/windows-hardware/drivers/ddi/netioddk/nf-netioddk-nmrregisterprovider">NmrRegisterProvider</a> function to
    register itself with the NMR.

The NMR calls a provider module's 
    <i>ProviderCleanupBindingContext</i> callback function at any IRQL <= DISPATCH_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_client_detach_provider_fn">ClientDetachProvider</a>



<a href="/windows-hardware/drivers/ddi/netioddk/ns-netioddk-_npi_provider_characteristics">NPI_PROVIDER_CHARACTERISTICS</a>



<a href="/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_provider_attach_client_fn">ProviderAttachClient</a>



<a href="/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_provider_detach_client_fn">ProviderDetachClient</a>

