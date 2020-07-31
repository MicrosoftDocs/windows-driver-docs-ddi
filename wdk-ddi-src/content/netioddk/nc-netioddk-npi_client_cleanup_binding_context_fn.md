---
UID: NC:netioddk.NPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN
title: NPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN (netioddk.h)
description: A client module's ClientCleanupBindingContext callback function performs any necessary cleanup and deallocation of the client module's binding context after the client module and a provider module have detached from one another.
old-location: netvista\clientcleanupbindingcontext.htm
tech.root: netvista
ms.assetid: eebffed4-a2e0-4743-871b-f50f0cdda30d
ms.date: 05/02/2018
keywords: ["NPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN callback function"]
ms.keywords: ClientCleanupBindingContext, ClientCleanupBindingContext callback function [Network Drivers Starting with Windows Vista], NPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN, NPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN callback, PNPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN, PNPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN callback function [Network Drivers Starting with Windows Vista], netioddk/ClientCleanupBindingContext, netvista.clientcleanupbindingcontext, nmrref_75483511-e903-4f9d-bc78-29e823b22f8f.xml
f1_keywords:
 - "netioddk/PNPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN"
 - "PNPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- netioddk.h
api_name:
- PNPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN
targetos: Windows
req.typenames: 
---

# NPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN callback function


## -description


A client module's 
  <i>ClientCleanupBindingContext</i> callback function performs any necessary cleanup and deallocation of the
  client module's binding context after the client module and a provider module have detached from one
  another.


## -parameters




### -param ClientBindingContext [in]

A pointer to the client module's context for the binding between the client module and the
     provider module from which it has detached. The client module passes this pointer to the NMR when it
     calls the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nf-netioddk-nmrclientattachprovider">NmrClientAttachProvider</a> function
     to attach to the provider module.


## -remarks



The NMR calls a client module's 
    <i>ClientCleanupBindingContext</i> callback function after the client module and a provider module have
    detached from one another.

A client module's 
    <i>ClientCleanupBindingContext</i> callback function should perform any necessary cleanup of the data
    contained within the client module's binding context structure. It should then free the memory for the
    binding context structure if the client module dynamically allocated the memory for the structure.

If the client module does not dynamically allocate the memory for its binding context and no other
    cleanup of its binding context is required, then the client module does not need to implement a 
    <i>ClientCleanupBindingContext</i> callback function. If the client module does not implement a 
    <i>ClientCleanupBindingContext</i> callback function, then it must set the 
    <i>ClientCleanupBindingContext</i> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/ns-netioddk-_npi_client_characteristics">
    NPI_CLIENT_CHARACTERISTICS</a> structure to <b>NULL</b> when it calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nf-netioddk-nmrregisterclient">NmrRegisterClient</a> function to register
    itself with the NMR.

The NMR calls a client module's 
    <i>ClientCleanupBindingContext</i> callback function at any IRQL <= DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_client_attach_provider_fn">ClientAttachProvider</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_client_detach_provider_fn">ClientDetachProvider</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/ns-netioddk-_npi_client_characteristics">NPI_CLIENT_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nf-netioddk-nmrclientattachprovider">NmrClientAttachProvider</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_provider_detach_client_fn">ProviderDetachClient</a>
 

 

