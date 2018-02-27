---
UID: NA:netioddk
ms.assetid: 5dc52805-9520-3ac9-bc97-e7ef6ccc33de
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Netioddk.h header



This header is used by Networking drivers for Windows Vista and later. For more information, see
- [Networking drivers for Windows Vista and later](../_netvista/index.md)

Netioddk.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [NmrClientAttachProvider function](nf-netioddk-nmrclientattachprovider.md) | The NmrClientAttachProvider function attaches a client module to a provider module. |
| [NmrClientDetachProviderComplete function](nf-netioddk-nmrclientdetachprovidercomplete.md) | The NmrClientDetachProviderComplete function notifies the NMR that a client module has completed detaching from a provider module. |
| [NmrDeregisterClient function](nf-netioddk-nmrderegisterclient.md) | The NmrDeregisterClient function deregisters a client module from the NMR. |
| [NmrDeregisterProvider function](nf-netioddk-nmrderegisterprovider.md) | The NmrDeregisterProvider function deregisters a provider module from the NMR. |
| [NmrProviderDetachClientComplete function](nf-netioddk-nmrproviderdetachclientcomplete.md) | The NmrProviderDetachClientComplete function notifies the NMR that a provider module has completed detaching from a client module. |
| [NmrRegisterClient function](nf-netioddk-nmrregisterclient.md) | The NmrRegisterClient function registers a client module with the NMR. |
| [NmrRegisterProvider function](nf-netioddk-nmrregisterprovider.md) | The NmrRegisterProvider function registers a provider module with the NMR. |
| [NmrWaitForClientDeregisterComplete function](nf-netioddk-nmrwaitforclientderegistercomplete.md) | The NmrWaitForClientDeregisterComplete function waits for the deregistration of a client module to complete. |
| [NmrWaitForProviderDeregisterComplete function](nf-netioddk-nmrwaitforproviderderegistercomplete.md) | The NmrWaitForProviderDeregisterComplete function waits for the deregistration of a provider module to complete. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [NPI_CLIENT_ATTACH_PROVIDER_FN callback](nc-netioddk-npi_client_attach_provider_fn.md) | A client module's ClientAttachProvider callback function attaches the client module to a provider module. |
| [NPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN callback](nc-netioddk-npi_client_cleanup_binding_context_fn.md) | A client module's ClientCleanupBindingContext callback function performs any necessary cleanup and deallocation of the client module's binding context after the client module and a provider module have detached from one another. |
| [NPI_CLIENT_DETACH_PROVIDER_FN callback](nc-netioddk-npi_client_detach_provider_fn.md) | A client module's ClientDetachProvider callback function detaches the client module from a provider module. |
| [NPI_PROVIDER_ATTACH_CLIENT_FN callback](nc-netioddk-npi_provider_attach_client_fn.md) | A provider module's ProviderAttachClient callback function attaches the provider module to a client module. |
| [NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN callback](nc-netioddk-npi_provider_cleanup_binding_context_fn.md) | A provider module's ProviderCleanupBindingContext callback function performs any necessary cleanup and deallocation of the provider module's binding context after the provider module and a client module have detached from one another. |
| [NPI_PROVIDER_DETACH_CLIENT_FN callback](nc-netioddk-npi_provider_detach_client_fn.md) | A provider module's ProviderDetachClient callback function detaches the provider module from a client module. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_NPI_CLIENT_CHARACTERISTICS structure](ns-netioddk-_npi_client_characteristics.md) | The NPI_CLIENT_CHARACTERISTICS structure defines the characteristics of a client module. |
| [_NPI_PROVIDER_CHARACTERISTICS structure](ns-netioddk-_npi_provider_characteristics.md) | The NPI_PROVIDER_CHARACTERISTICS structure defines the characteristics of a provider module. |
| [_NPI_REGISTRATION_INSTANCE structure](ns-netioddk-_npi_registration_instance.md) | The NPI_REGISTRATION_INSTANCE structure defines the data related to the registration of a network module with the NMR. |
