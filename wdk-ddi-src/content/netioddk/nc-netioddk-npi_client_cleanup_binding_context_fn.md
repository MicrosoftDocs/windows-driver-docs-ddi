---
UID: NC:netioddk.NPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN
title: NPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN
author: windows-driver-content
description: A client module's ClientCleanupBindingContext callback function performs any necessary cleanup and deallocation of the client module's binding context after the client module and a provider module have detached from one another.
old-location: netvista\clientcleanupbindingcontext.htm
old-project: netvista
ms.assetid: eebffed4-a2e0-4743-871b-f50f0cdda30d
ms.author: windowsdriverdev
ms.date: 3/26/2018
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
product:
- Windows
targetos: Windows
req.typenames: NET_DMA_PROVIDER_CHARACTERISTICS, *PNET_DMA_PROVIDER_CHARACTERISTICS
---

# NPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN callback


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
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568770">NmrClientAttachProvider</a> function
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
    <a href="https://msdn.microsoft.com/03d73a80-0860-4ec7-8eb1-5954f64b6026">
    NPI_CLIENT_CHARACTERISTICS</a> structure to <b>NULL</b> when it calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568782">NmrRegisterClient</a> function to register
    itself with the NMR.

The NMR calls a client module's 
    <i>ClientCleanupBindingContext</i> callback function at any IRQL &lt;= DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/8f8abdb1-d018-4404-a80a-74017c324a0f">ClientAttachProvider</a>



<a href="https://msdn.microsoft.com/a684136a-e2f2-4f82-9e9a-166b40bd7536">ClientDetachProvider</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568812">NPI_CLIENT_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568770">NmrClientAttachProvider</a>



<a href="https://msdn.microsoft.com/0f29bf89-856c-4019-a966-3e666a7fc78d">ProviderDetachClient</a>
 

 

