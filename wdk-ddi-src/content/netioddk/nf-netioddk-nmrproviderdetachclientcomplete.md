---
UID: NF:netioddk.NmrProviderDetachClientComplete
title: NmrProviderDetachClientComplete function
author: windows-driver-content
description: The NmrProviderDetachClientComplete function notifies the NMR that a provider module has completed detaching from a client module.
old-location: netvista\nmrproviderdetachclientcomplete.htm
old-project: netvista
ms.assetid: a52b3cfc-d6bd-4569-8b09-36dce65d017f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NmrProviderDetachClientComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: netioddk.h
req.include-header: Wsk.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NmrProviderDetachClientComplete
req.alt-loc: netio.lib,netio.dll
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
req.typenames: *PNET_DMA_PROVIDER_CHARACTERISTICS, NET_DMA_PROVIDER_CHARACTERISTICS
---

# NmrProviderDetachClientComplete function



## -description
The 
  <b>NmrProviderDetachClientComplete</b> function notifies the NMR that a provider module has completed
  detaching from a client module.



## -syntax

````
VOID NmrProviderDetachClientComplete(
  _In_ HANDLE NmrBindingHandle
);
````


## -parameters

### -param NmrBindingHandle [in]

A handle used by the NMR to represent the binding between the client module and the provider
     module. The NMR passes this handle to the provider module when it calls the provider module's 
     <a href="..\netioddk\nc-netioddk-npi_provider_attach_client_fn.md">ProviderAttachClient</a> callback
     function.


## -returns
None


## -remarks
A provider module calls the 
    <b>NmrProviderDetachClientComplete</b> function when it asynchronously completes detaching from a client
    module after returning STATUS_PENDING from its 
    <a href="..\netioddk\nc-netioddk-npi_provider_detach_client_fn.md">ProviderDetachClient</a> callback
    function.

A provider module should not call the 
    <b>NmrProviderDetachClientComplete</b> function if it returns STATUS_SUCCESS from its 
    <a href="..\netioddk\nc-netioddk-npi_provider_detach_client_fn.md">ProviderDetachClient</a> callback
    function.


## -see-also
<dl>
<dt>
<a href="..\netioddk\nc-netioddk-npi_provider_attach_client_fn.md">ProviderAttachClient</a>
</dt>
<dt>
<a href="..\netioddk\nc-netioddk-npi_provider_detach_client_fn.md">ProviderDetachClient</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NmrProviderDetachClientComplete function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

