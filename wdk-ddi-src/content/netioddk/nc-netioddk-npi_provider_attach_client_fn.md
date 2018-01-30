---
UID: NC:netioddk.NPI_PROVIDER_ATTACH_CLIENT_FN
title: NPI_PROVIDER_ATTACH_CLIENT_FN
author: windows-driver-content
description: A provider module's ProviderAttachClient callback function attaches the provider module to a client module.
old-location: netvista\providerattachclient.htm
old-project: netvista
ms.assetid: 6c8e6cf1-0528-4da2-acc1-81ec9dbc23c3
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.providerattachclient, ProviderAttachClient callback function [Network Drivers Starting with Windows Vista], ProviderAttachClient, NPI_PROVIDER_ATTACH_CLIENT_FN, NPI_PROVIDER_ATTACH_CLIENT_FN, netioddk/ProviderAttachClient, PNPI_PROVIDER_ATTACH_CLIENT_FN callback function [Network Drivers Starting with Windows Vista], PNPI_PROVIDER_ATTACH_CLIENT_FN, nmrref_7b693216-cb96-4608-aae0-77ddde6dc28c.xml
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	netioddk.h
apiname:
-	PNPI_PROVIDER_ATTACH_CLIENT_FN
product: Windows
targetos: Windows
req.typenames: NET_DMA_PROVIDER_CHARACTERISTICS, *PNET_DMA_PROVIDER_CHARACTERISTICS
---

# NPI_PROVIDER_ATTACH_CLIENT_FN callback


## -description


A provider module's 
  <i>ProviderAttachClient</i> callback function attaches the provider module to a client module.


## -prototype


````
NPI_PROVIDER_ATTACH_CLIENT_FN ProviderAttachClient;

NTSTATUS ProviderAttachClient(
  _In_        HANDLE                     NmrBindingHandle,
  _In_        PVOID                      ProviderContext,
  _In_        PNPI_REGISTRATION_INSTANCE ClientRegistrationInstance,
  _In_        PVOID                      ClientBindingContext,
  _In_  const VOID                       *ClientDispatch,
  _Out_       PVOID                      *ProviderBindingContext,
  _Out_ const VOID                       **ProviderDispatch
)
{ ... }

typedef NPI_PROVIDER_ATTACH_CLIENT_FN * PNPI_PROVIDER_ATTACH_CLIENT_FN;
````


## -parameters




### -param NmrBindingHandle [in]

A handle used by the NMR to represent the binding between the client module and the provider
     module.


### -param ProviderContext [in]

A pointer to the provider module's registration context. The provider module passes this pointer
     to the NMR when it calls the 
     <a href="..\netioddk\nf-netioddk-nmrregisterprovider.md">NmrRegisterProvider</a> function to
     register itself with the NMR.


### -param ClientRegistrationInstance [in]

A pointer to an 
     <mshelp:link keywords="netvista.npi_registration_instance" tabindex="0"><b>
     NPI_REGISTRATION_INSTANCE</b></mshelp:link> structure. This structure contains the client module's registration
     data.


### -param ClientBindingContext [in]

A pointer to the client module's context for the binding between the client module and the
     provider module. The client module uses this context to keep track of the state of the binding. The
     contents of the client module's binding context are opaque to the provider module. The provider module
     passes this pointer to the client module whenever it calls any of the client module's 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> callback functions that
     require the client module's binding context.


### -param *ClientDispatch



### -param *ProviderBindingContext



### -param **ProviderDispatch






#### - ClientDispatch [in]

A pointer to a constant structure that contains the dispatch table of 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> callback functions for the
     client module. The contents of the structure are 
     NPI-specific. If the 
     NPI does not define a client
     dispatch table structure, then this pointer is <b>NULL</b>.


#### - ProviderBindingContext [out]

A pointer to a variable into which the provider module will store a pointer to its context for the
     binding between the client module and the provider module. The provider module uses this context to keep
     track of the state of the binding. The contents of the provider module's binding context are opaque to
     the client module. The client module passes this pointer to the provider module whenever it calls one of
     the provider module's 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> functions that require the
     provider module's binding context. The provider module must make sure that this context remains valid
     and resident in memory as long as the client module is attached to the provider module.


#### - ProviderDispatch [out]

A pointer to a variable into which the provider module will store a pointer to a constant
     structure that contains the dispatch table of 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> functions for the provider
     module. The provider module must make sure that this structure remains valid and resident in memory as
     long as the client module is attached to the provider module. The contents of the structure are 
     NPI-specific.


## -returns


A provider module's 
     <i>ProviderAttachClient</i> callback function returns one of the following NTSTATUS codes:
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
The provider module successfully attached to the client module.

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


The NMR calls a provider module's 
    <i>ProviderAttachClient</i> callback function whenever a client module calls the 
    <a href="..\netioddk\nf-netioddk-nmrclientattachprovider.md">NmrClientAttachProvider</a> function
    with a handle that represents a binding between the client module and the provider module.

A provider module can examine the client module's registration data. This data is in the structure
    pointed to by the 
    <i>ClientRegistrationInstance</i> parameter. The provider module uses this data to determine whether it
    will attach to the client module:
<ul>
<li>If the provider module determines that it will attach to the client module, then the 
     <i>ProviderAttachClient</i> callback function must do the following:
     <ol>
<li>Save the pointers passed in the 
      <i>ClientBindingContext</i> and 
      <i>ClientDispatch</i> parameters so that the provider module can make calls to the client module's 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> functions.</li>
<li>Save the handle passed in the 
      <i>NmrBindingHandle</i> parameter. The provider module passes this handle as a parameter to the 
      <mshelp:link keywords="netvista.nmrproviderdetachclientcomplete" tabindex="0"><b>
      NmrProviderDetachClientComplete</b></mshelp:link> function when it detaches from the client module.</li>
<li>Set the 
      <i>ProviderBindingContext</i> parameter to point to the provider module's binding context structure for
      the binding between the client module and the provider module.</li>
<li>Set the 
      <i>ProviderDispatch</i> parameter to point to a structure that contains the provider module's dispatch
      table of 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> functions.</li>
<li>Return STATUS_SUCCESS.</li>
</ol>
</li>
<li>
If the provider module determines that it will not attach to the client module, then the 
      <i>ProviderAttachClient</i> callback function must return STATUS_NOINTERFACE.

</li>
</ul>If the provider module attaches to the client module and it dynamically allocated memory for its
    binding context, it should free that allocated memory when the NMR calls the provider module's 
    <mshelp:link keywords="netvista.providercleanupbindingcontext" tabindex="0"><i>
    ProviderCleanupBindingContext</i></mshelp:link> callback function after the client module and provider module are
    detached from each other.

The NMR calls a provider module's 
    <i>ProviderAttachClient</i> callback function at IRQL = PASSIVE_LEVEL.



## -see-also

<a href="..\netioddk\ns-netioddk-_npi_registration_instance.md">NPI_REGISTRATION_INSTANCE</a>

<a href="..\netioddk\ns-netioddk-_npi_provider_characteristics.md">NPI_PROVIDER_CHARACTERISTICS</a>

<a href="..\netioddk\nc-netioddk-npi_provider_detach_client_fn.md">ProviderDetachClient</a>

<a href="..\netioddk\nf-netioddk-nmrclientattachprovider.md">NmrClientAttachProvider</a>

<a href="..\netioddk\nf-netioddk-nmrregisterprovider.md">NmrRegisterProvider</a>

<mshelp:link keywords="netvista.nmrproviderdetachclientcomplete" tabindex="0"><b>
   NmrProviderDetachClientComplete</b></mshelp:link>

<mshelp:link keywords="netvista.providercleanupbindingcontext" tabindex="0"><i>
   ProviderCleanupBindingContext</i></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NPI_PROVIDER_ATTACH_CLIENT_FN callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

