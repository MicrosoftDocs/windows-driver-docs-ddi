---
UID: NC:netioddk.NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN
title: NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN
author: windows-driver-content
description: A provider module's ProviderCleanupBindingContext callback function performs any necessary cleanup and deallocation of the provider module's binding context after the provider module and a client module have detached from one another.
old-location: netvista\providercleanupbindingcontext.htm
tech.root: netvista
ms.assetid: 0af476f6-0113-4aeb-b7d6-8e0e64a89bd0
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN, NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN callback, PNPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN, PNPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN callback function [Network Drivers Starting with Windows Vista], ProviderCleanupBindingContext, ProviderCleanupBindingContext callback function [Network Drivers Starting with Windows Vista], netioddk/ProviderCleanupBindingContext, netvista.providercleanupbindingcontext, nmrref_9723dfb1-96dd-410c-a5cd-1adfb6aa9544.xml
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# NPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN callback function


## -description


A provider module's 
  <i>ProviderCleanupBindingContext</i> callback function performs any necessary cleanup and deallocation of
  the provider module's binding context after the provider module and a client module have detached from one
  another.


## -parameters




### -param ProviderBindingContext [in]

A pointer to the provider module's context for the binding between the provider module and the
     client module from which it has detached. The provider module's 
     <a href="https://msdn.microsoft.com/6c8e6cf1-0528-4da2-acc1-81ec9dbc23c3">ProviderAttachClient</a> callback
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
    <a href="https://msdn.microsoft.com/a83220e8-496c-4b83-b774-88ab1f017e8d">
    NPI_PROVIDER_CHARACTERISTICS</a> structure to <b>NULL</b> when it calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568784">NmrRegisterProvider</a> function to
    register itself with the NMR.

The NMR calls a provider module's 
    <i>ProviderCleanupBindingContext</i> callback function at any IRQL &lt;= DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/a684136a-e2f2-4f82-9e9a-166b40bd7536">ClientDetachProvider</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568814">NPI_PROVIDER_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/6c8e6cf1-0528-4da2-acc1-81ec9dbc23c3">ProviderAttachClient</a>



<a href="https://msdn.microsoft.com/0f29bf89-856c-4019-a966-3e666a7fc78d">ProviderDetachClient</a>
 

 

