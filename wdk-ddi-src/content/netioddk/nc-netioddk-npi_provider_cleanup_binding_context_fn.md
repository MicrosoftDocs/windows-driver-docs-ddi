---
UID: NC:netioddk.NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN
title: NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN
author: windows-driver-content
description: A provider module's ProviderCleanupBindingContext callback function performs any necessary cleanup and deallocation of the provider module's binding context after the provider module and a client module have detached from one another.
old-location: netvista\providercleanupbindingcontext.htm
old-project: netvista
ms.assetid: 0af476f6-0113-4aeb-b7d6-8e0e64a89bd0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN, PNPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN, PNPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN callback function [Network Drivers Starting with Windows Vista], ProviderCleanupBindingContext, ProviderCleanupBindingContext callback function [Network Drivers Starting with Windows Vista], netioddk/ProviderCleanupBindingContext, netvista.providercleanupbindingcontext, nmrref_9723dfb1-96dd-410c-a5cd-1adfb6aa9544.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	netioddk.h
api_name:
-	PNPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN
product: Windows
targetos: Windows
req.typenames: NET_DMA_PROVIDER_CHARACTERISTICS, *PNET_DMA_PROVIDER_CHARACTERISTICS
---

# NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN callback


## -description


A provider module's 
  <i>ProviderCleanupBindingContext</i> callback function performs any necessary cleanup and deallocation of
  the provider module's binding context after the provider module and a client module have detached from one
  another.


## -prototype


````
NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN ProviderCleanupBindingContext;

VOID ProviderCleanupBindingContext(
  _In_ PVOID ProviderBindingContext
)
{ ... }

typedef NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN * PNPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN;
````


## -parameters




### -param ProviderBindingContext [in]

A pointer to the provider module's context for the binding between the provider module and the
     client module from which it has detached. The provider module's 
     <a href="..\netioddk\nc-netioddk-npi_provider_attach_client_fn.md">ProviderAttachClient</a> callback
     function returns this pointer to the NMR when it attaches to the client module.


## -returns



None




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
    <a href="..\netioddk\ns-netioddk-_npi_provider_characteristics.md">
    NPI_PROVIDER_CHARACTERISTICS</a> structure to <b>NULL</b> when it calls the 
    <a href="..\netioddk\nf-netioddk-nmrregisterprovider.md">NmrRegisterProvider</a> function to
    register itself with the NMR.

The NMR calls a provider module's 
    <i>ProviderCleanupBindingContext</i> callback function at any IRQL &lt;= DISPATCH_LEVEL.




## -see-also

<a href="..\netioddk\nc-netioddk-npi_provider_detach_client_fn.md">ProviderDetachClient</a>



<a href="..\netioddk\nc-netioddk-npi_client_detach_provider_fn.md">ClientDetachProvider</a>



<a href="..\netioddk\nc-netioddk-npi_provider_attach_client_fn.md">ProviderAttachClient</a>



<a href="..\netioddk\ns-netioddk-_npi_provider_characteristics.md">NPI_PROVIDER_CHARACTERISTICS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

