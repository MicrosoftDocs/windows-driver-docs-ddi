---
UID: NC:netioddk.NPI_CLIENT_DETACH_PROVIDER_FN
title: NPI_CLIENT_DETACH_PROVIDER_FN
author: windows-driver-content
description: A client module's ClientDetachProvider callback function detaches the client module from a provider module.
old-location: netvista\clientdetachprovider.htm
old-project: netvista
ms.assetid: a684136a-e2f2-4f82-9e9a-166b40bd7536
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NET_DMA_PROVIDER_CHARACTERISTICS, *PNET_DMA_PROVIDER_CHARACTERISTICS, NET_DMA_PROVIDER_CHARACTERISTICS
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
req.alt-api: PNPI_CLIENT_DETACH_PROVIDER_FN
req.alt-loc: netioddk.h
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
req.typenames: *PNET_DMA_PROVIDER_CHARACTERISTICS, NET_DMA_PROVIDER_CHARACTERISTICS
---

# NPI_CLIENT_DETACH_PROVIDER_FN callback



## -description
A client module's 
  <i>ClientDetachProvider</i> callback function detaches the client module from a provider module.



## -prototype

````
NPI_CLIENT_DETACH_PROVIDER_FN ClientDetachProvider;

NTSTATUS ClientDetachProvider(
  _In_ PVOID ClientBindingContext
)
{ ... }

typedef NPI_CLIENT_DETACH_PROVIDER_FN * PNPI_CLIENT_DETACH_PROVIDER_FN;
````


## -parameters

### -param ClientBindingContext [in]

A pointer to the client module's context for the binding between the client module and the
     provider module from which it is detaching. The client module passes this pointer to the NMR when it
     calls the 
     <a href="..\netioddk\nf-netioddk-nmrclientattachprovider.md">NmrClientAttachProvider</a> function
     to attach to the provider module.


## -returns
A client module's 
     <i>ClientDetachProvider</i> callback function returns one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The client module successfully detached from the provider module.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>The client module could not detach from the provider module immediately.

 


## -remarks
The NMR calls a client module's 
    <i>ClientDetachProvider</i> callback function whenever the binding between the client module and a
    provider module needs to be terminated. Detachment is initiated by either the client module calling the 
    <a href="..\netioddk\nf-netioddk-nmrderegisterclient.md">NmrDeregisterClient</a> function or the
    provider module calling the 
    <a href="..\netioddk\nf-netioddk-nmrderegisterprovider.md">NmrDeregisterProvider</a> function.

After its 
    <i>ClientDetachProvider</i> callback function has been called, a client module should not make any more
    calls to any of the provider module's 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> functions. If there are no
    in-progress calls to any of the provider module's 
    NPI functions when the client
    module's 
    <i>ClientDetachProvider</i> callback function is called, the client module's 
    <i>ClientDetachProvider</i> callback function returns STATUS_SUCCESS.

If there are in-progress calls to one or more of the provider module's 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> functions when the client
    module's 
    <i>ClientDetachProvider</i> callback function is called, then the client module's 
    <i>ClientDetachProvider</i> callback function returns STATUS_PENDING. In this situation, the client module
    must call the 
    <a href="..\netioddk\nf-netioddk-nmrclientdetachprovidercomplete.md">
    NmrClientDetachProviderComplete</a> function after all in-progress calls to the provider module's 
    NPI functions have completed. The
    call to the 
    <b>
    NmrClientDetachProviderComplete</b> function notifies the NMR that detachment from the provider module
    is complete.

The NMR calls the client module's 
    <a href="..\netioddk\nc-netioddk-npi_client_cleanup_binding_context_fn.md">
    ClientCleanupBindingContext</a> callback function and the provider module's 
    <a href="..\netioddk\nc-netioddk-npi_provider_cleanup_binding_context_fn.md">
    ProviderCleanupBindingContext</a> callback function after both the client module and the provider
    module have completed detachment from each other.

The NMR calls a client module's 
    <i>ClientDetachProvider</i> callback function at any IRQL &lt;= DISPATCH_LEVEL.


## -see-also
<dl>
<dt>
<a href="..\netioddk\nf-netioddk-nmrclientattachprovider.md">NmrClientAttachProvider</a>
</dt>
<dt>
<a href="..\netioddk\nf-netioddk-nmrclientdetachprovidercomplete.md">
   NmrClientDetachProviderComplete</a>
</dt>
<dt>
<a href="..\netioddk\nf-netioddk-nmrderegisterclient.md">NmrDeregisterClient</a>
</dt>
<dt>
<a href="..\netioddk\nf-netioddk-nmrderegisterprovider.md">NmrDeregisterProvider</a>
</dt>
<dt>
<a href="..\netioddk\nc-netioddk-npi_client_cleanup_binding_context_fn.md">ClientCleanupBindingContext</a>
</dt>
<dt>
<a href="..\netioddk\nc-netioddk-npi_provider_cleanup_binding_context_fn.md">
   ProviderCleanupBindingContext</a>
</dt>
<dt>
<a href="..\netioddk\ns-netioddk-_npi_client_characteristics.md">NPI_CLIENT_CHARACTERISTICS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NPI_CLIENT_DETACH_PROVIDER_FN callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

