---
UID: NF:netioddk.NmrClientAttachProvider
title: NmrClientAttachProvider function (netioddk.h)
description: The NmrClientAttachProvider function attaches a client module to a provider module.
old-location: netvista\nmrclientattachprovider.htm
tech.root: netvista
ms.assetid: dca8f82b-f058-4765-890c-973f8462c2f5
ms.date: 05/02/2018
ms.keywords: NmrClientAttachProvider, NmrClientAttachProvider function [Network Drivers Starting with Windows Vista], netioddk/NmrClientAttachProvider, netvista.nmrclientattachprovider, nmrref_6d66009c-5262-4a75-986d-1eb91dcc61a2.xml
ms.topic: function
req.header: netioddk.h
req.include-header: Wsk.h
req.target-type: Desktop
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
req.lib: Netio.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- netio.lib
- netio.dll
api_name:
- NmrClientAttachProvider
product:
- Windows
targetos: Windows
req.typenames: 
---

# NmrClientAttachProvider function


## -description


The 
  <b>NmrClientAttachProvider</b> function attaches a client module to a provider module.


## -parameters




### -param NmrBindingHandle [in]

A handle used by the NMR to represent the binding between the client module and the provider
     module. The NMR passes this handle to the client module when it calls the client module's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netioddk/nc-netioddk-npi_client_attach_provider_fn">ClientAttachProvider</a> callback
     function.


### -param ClientBindingContext [in]

A pointer to a caller-supplied context for the binding between the client module and the provider
     module. The client module uses this context to keep track of the state of the binding. The contents of
     the client module's binding context are opaque to the provider module. The provider module passes this
     pointer to the client module whenever it calls any of the client module's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> callback functions that
     require the client module's binding context. The client module must make sure that this context remains
     valid and resident in memory as long as the provider module is attached to the client module.


### -param ClientDispatch [in]

A pointer to a constant structure that contains the dispatch table of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> callback functions for the
     client module. The client module must make sure that this structure remains valid and resident in memory
     as long as the provider module is attached to the client module. The contents of the structure are 
     NPI-specific. If the 
     NPI does not define a client
     dispatch table structure, the client module must set this parameter to <b>NULL</b>.


### -param ProviderBindingContext [out]

A pointer to a variable that receives a pointer to the provider module's context for the binding
     between the client module and the provider module. The provider module uses this context to keep track
     of the state of the binding. The contents of the provider module's binding context are opaque to the
     client module. The client module passes this pointer to the provider module whenever it calls any of the
     provider module's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> functions that require the
     provider module's binding context.


### -param ProviderDispatch [out]

A pointer to a variable that receives a pointer to a structure that contains the dispatch table of     
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> functions for the provider
     module. The contents of the structure are 
     NPI-specific.


## -returns



The 
     <b>NmrClientAttachProvider</b> function returns one of the following NTSTATUS codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The client module was successfully attached to the provider module.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The provider module did not attach to the client module.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>
 




## -remarks



A client module calls the 
    <b>NmrClientAttachProvider</b> function from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netioddk/nc-netioddk-npi_client_attach_provider_fn">ClientAttachProvider</a> callback
    function to attach itself to a provider module.

When a client module calls the 
    <b>NmrClientAttachProvider</b> function, the NMR calls the provider module's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netioddk/nc-netioddk-npi_provider_attach_client_fn">ProviderAttachClient</a> callback
    function to complete the attachment process. The 
    <b>NmrClientAttachProvider</b> function returns the status code that is returned by the provider module's 
    <i>ProviderAttachClient</i> callback
    function.

If the 
    <b>NmrClientAttachProvider</b> function does not return STATUS_SUCCESS, the client module should perform
    any necessary cleanup of the data contained within its binding context structure. The client module
    should then free the memory for its binding context structure if it dynamically allocated the memory for
    the structure.

If the 
    <b>NmrClientAttachProvider</b> function returns STATUS_SUCCESS and the client module dynamically allocated
    the memory for its binding context, the client module should free that allocated memory when the NMR
    calls the client module's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netioddk/nc-netioddk-npi_client_cleanup_binding_context_fn">
    ClientCleanupBindingContext</a> callback function after the client module and provider module are
    detached from each other.

If the 
    <b>NmrClientAttachProvider</b> function returns STATUS_SUCCESS, the client module must save the pointers
    returned in the 
    <i>ProviderBindingContext</i> and 
    <i>ProviderDispatch</i> parameters so that it can call the provider module's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> functions.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netioddk/nc-netioddk-npi_client_attach_provider_fn">ClientAttachProvider</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netioddk/nc-netioddk-npi_client_cleanup_binding_context_fn">ClientCleanupBindingContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netioddk/nc-netioddk-npi_provider_attach_client_fn">ProviderAttachClient</a>
 

 

