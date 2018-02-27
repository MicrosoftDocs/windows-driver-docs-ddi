---
UID: NC:netioddk.NPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN
title: NPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN
author: windows-driver-content
description: A client module's ClientCleanupBindingContext callback function performs any necessary cleanup and deallocation of the client module's binding context after the client module and a provider module have detached from one another.
old-location: netvista\clientcleanupbindingcontext.htm
old-project: netvista
ms.assetid: eebffed4-a2e0-4743-871b-f50f0cdda30d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ClientCleanupBindingContext, ClientCleanupBindingContext callback function [Network Drivers Starting with Windows Vista], NPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN, PNPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN, PNPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN callback function [Network Drivers Starting with Windows Vista], netioddk/ClientCleanupBindingContext, netvista.clientcleanupbindingcontext, nmrref_75483511-e903-4f9d-bc78-29e823b22f8f.xml
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
-	PNPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN
product: Windows
targetos: Windows
req.typenames: NET_DMA_PROVIDER_CHARACTERISTICS, *PNET_DMA_PROVIDER_CHARACTERISTICS
---

# NPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN callback


## -description


A client module's 
  <i>ClientCleanupBindingContext</i> callback function performs any necessary cleanup and deallocation of the
  client module's binding context after the client module and a provider module have detached from one
  another.


## -prototype


````
NPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN ClientCleanupBindingContext;

VOID ClientCleanupBindingContext(
  _In_ PVOID ClientBindingContext
)
{ ... }

typedef NPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN * PNPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN;
````


## -parameters




### -param ClientBindingContext [in]

A pointer to the client module's context for the binding between the client module and the
     provider module from which it has detached. The client module passes this pointer to the NMR when it
     calls the 
     <a href="..\netioddk\nf-netioddk-nmrclientattachprovider.md">NmrClientAttachProvider</a> function
     to attach to the provider module.


## -returns



None




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
    <a href="..\netioddk\ns-netioddk-_npi_client_characteristics.md">
    NPI_CLIENT_CHARACTERISTICS</a> structure to <b>NULL</b> when it calls the 
    <a href="..\netioddk\nf-netioddk-nmrregisterclient.md">NmrRegisterClient</a> function to register
    itself with the NMR.

The NMR calls a client module's 
    <i>ClientCleanupBindingContext</i> callback function at any IRQL &lt;= DISPATCH_LEVEL.




## -see-also

<a href="..\netioddk\ns-netioddk-_npi_client_characteristics.md">NPI_CLIENT_CHARACTERISTICS</a>



<a href="..\netioddk\nc-netioddk-npi_client_detach_provider_fn.md">ClientDetachProvider</a>



<a href="..\netioddk\nc-netioddk-npi_provider_detach_client_fn.md">ProviderDetachClient</a>



<a href="..\netioddk\nf-netioddk-nmrclientattachprovider.md">NmrClientAttachProvider</a>



<a href="..\netioddk\nc-netioddk-npi_client_attach_provider_fn.md">ClientAttachProvider</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

