---
UID: NS:netioddk._NPI_PROVIDER_CHARACTERISTICS
title: _NPI_PROVIDER_CHARACTERISTICS (netioddk.h)
description: The NPI_PROVIDER_CHARACTERISTICS structure defines the characteristics of a provider module.
old-location: netvista\npi_provider_characteristics.htm
tech.root: netvista
ms.assetid: a83220e8-496c-4b83-b774-88ab1f017e8d
ms.date: 05/02/2018
keywords: ["_NPI_PROVIDER_CHARACTERISTICS structure"]
ms.keywords: NPI_PROVIDER_CHARACTERISTICS, NPI_PROVIDER_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNPI_PROVIDER_CHARACTERISTICS, PNPI_PROVIDER_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NPI_PROVIDER_CHARACTERISTICS, netioddk/NPI_PROVIDER_CHARACTERISTICS, netioddk/PNPI_PROVIDER_CHARACTERISTICS, netvista.npi_provider_characteristics, nmrref_ceebed62-8102-41e3-af13-e663c1e8babb.xml
f1_keywords:
 - "netioddk/NPI_PROVIDER_CHARACTERISTICS"
 - "NPI_PROVIDER_CHARACTERISTICS"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- netioddk.h
api_name:
- NPI_PROVIDER_CHARACTERISTICS
targetos: Windows
req.typenames: NPI_PROVIDER_CHARACTERISTICS
---

# _NPI_PROVIDER_CHARACTERISTICS structure


## -description


The NPI_PROVIDER_CHARACTERISTICS structure defines the characteristics of a provider module.


## -struct-fields




### -field Version

The version of the NMR with which the provider is registering. A provider module should set this
     member to zero.


### -field Length

The size, in bytes, of the NPI_PROVIDER_CHARACTERISTICS structure.


### -field ProviderAttachClient

A pointer to the provider module's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_provider_attach_client_fn">ProviderAttachClient</a> callback
     function.


### -field ProviderDetachClient

A pointer to the provider module's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_provider_detach_client_fn">ProviderDetachClient</a> callback
     function.


### -field ProviderCleanupBindingContext

A pointer to the provider module's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_provider_cleanup_binding_context_fn">
     ProviderCleanupBindingContext</a> callback function. If the provider module does not dynamically
     allocate the memory for its binding context and no other cleanup of its binding context is required,
     then the provider module does not need to implement a 
     <i>
     ProviderCleanupBindingContext</i> callback function. If the provider module does not implement a 
     <i>
     ProviderCleanupBindingContext</i> callback function, then this member must be set to <b>NULL</b>.


### -field ProviderRegistrationInstance

An 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/ns-netioddk-_npi_registration_instance">
     NPI_REGISTRATION_INSTANCE</a> structure that specifies the identity of the provider module and the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> for which it is
     registering.


## -remarks



A provider module passes a pointer to an NPI_PROVIDER_CHARACTERISTICS structure to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nf-netioddk-nmrregisterprovider">NmrRegisterProvider</a> function when it
    registers itself with the NMR.

A provider module must make sure that this structure remains valid and resident in memory as long as
    the provider module is registered with the NMR.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/ns-netioddk-_npi_registration_instance">NPI_REGISTRATION_INSTANCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nf-netioddk-nmrregisterprovider">NmrRegisterProvider</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_provider_attach_client_fn">ProviderAttachClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_provider_cleanup_binding_context_fn">
   ProviderCleanupBindingContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_provider_detach_client_fn">ProviderDetachClient</a>
 

 

