---
UID: NC:netioddk.NPI_PROVIDER_ATTACH_CLIENT_FN
title: NPI_PROVIDER_ATTACH_CLIENT_FN
author: windows-driver-content
description: A provider module's ProviderAttachClient callback function attaches the provider module to a client module.
old-location: netvista\providerattachclient.htm
tech.root: netvista
ms.assetid: 6c8e6cf1-0528-4da2-acc1-81ec9dbc23c3
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NPI_PROVIDER_ATTACH_CLIENT_FN, NPI_PROVIDER_ATTACH_CLIENT_FN callback, PNPI_PROVIDER_ATTACH_CLIENT_FN, PNPI_PROVIDER_ATTACH_CLIENT_FN callback function [Network Drivers Starting with Windows Vista], ProviderAttachClient, ProviderAttachClient callback function [Network Drivers Starting with Windows Vista], netioddk/ProviderAttachClient, netvista.providerattachclient, nmrref_7b693216-cb96-4608-aae0-77ddde6dc28c.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	netioddk.h
api_name:
-	PNPI_PROVIDER_ATTACH_CLIENT_FN
product:
- Windows
targetos: Windows
req.typenames: 
---

# NPI_PROVIDER_ATTACH_CLIENT_FN callback function


## -description


A provider module's 
  <i>ProviderAttachClient</i> callback function attaches the provider module to a client module.


## -parameters




### -param NmrBindingHandle [in]

A handle used by the NMR to represent the binding between the client module and the provider
     module.


### -param ProviderContext [in]

A pointer to the provider module's registration context. The provider module passes this pointer
     to the NMR when it calls the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568784">NmrRegisterProvider</a> function to
     register itself with the NMR.


### -param ClientRegistrationInstance [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/a368f9d9-a7e0-4b35-ba14-b0919f74029d">
     NPI_REGISTRATION_INSTANCE</a> structure. This structure contains the client module's registration
     data.


### -param ClientBindingContext [in]

A pointer to the client module's context for the binding between the client module and the
     provider module. The client module uses this context to keep track of the state of the binding. The
     contents of the client module's binding context are opaque to the provider module. The provider module
     passes this pointer to the client module whenever it calls any of the client module's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> callback functions that
     require the client module's binding context.


### -param *ClientDispatch [in]

A pointer to a constant structure that contains the dispatch table of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> callback functions for the
     client module. The contents of the structure are 
     NPI-specific. If the 
     NPI does not define a client
     dispatch table structure, then this pointer is <b>NULL</b>.


### -param *ProviderBindingContext [out]

A pointer to a variable into which the provider module will store a pointer to its context for the
     binding between the client module and the provider module. The provider module uses this context to keep
     track of the state of the binding. The contents of the provider module's binding context are opaque to
     the client module. The client module passes this pointer to the provider module whenever it calls one of
     the provider module's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> functions that require the
     provider module's binding context. The provider module must make sure that this context remains valid
     and resident in memory as long as the client module is attached to the provider module.


#### - **ProviderDispatch [out]

A pointer to a variable into which the provider module will store a pointer to a constant
     structure that contains the dispatch table of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> functions for the provider
     module. The provider module must make sure that this structure remains valid and resident in memory as
     long as the client module is attached to the provider module. The contents of the structure are 
     NPI-specific.


#### - ProviderDispatch [out]

A pointer to a variable into which the provider module will store a pointer to a constant
     structure that contains the dispatch table of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> functions for the provider
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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568770">NmrClientAttachProvider</a> function
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
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> functions.</li>
<li>Save the handle passed in the 
      <i>NmrBindingHandle</i> parameter. The provider module passes this handle as a parameter to the 
      <a href="https://msdn.microsoft.com/a52b3cfc-d6bd-4569-8b09-36dce65d017f">
      NmrProviderDetachClientComplete</a> function when it detaches from the client module.</li>
<li>Set the 
      <i>ProviderBindingContext</i> parameter to point to the provider module's binding context structure for
      the binding between the client module and the provider module.</li>
<li>Set the 
      <i>ProviderDispatch</i> parameter to point to a structure that contains the provider module's dispatch
      table of 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> functions.</li>
<li>Return STATUS_SUCCESS.</li>
</ol>
</li>
<li>
If the provider module determines that it will not attach to the client module, then the 
      <i>ProviderAttachClient</i> callback function must return STATUS_NOINTERFACE.

</li>
</ul>
If the provider module attaches to the client module and it dynamically allocated memory for its
    binding context, it should free that allocated memory when the NMR calls the provider module's 
    <a href="https://msdn.microsoft.com/0af476f6-0113-4aeb-b7d6-8e0e64a89bd0">
    ProviderCleanupBindingContext</a> callback function after the client module and provider module are
    detached from each other.

The NMR calls a provider module's 
    <i>ProviderAttachClient</i> callback function at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568814">NPI_PROVIDER_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568815">NPI_REGISTRATION_INSTANCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568770">NmrClientAttachProvider</a>



<a href="https://msdn.microsoft.com/a52b3cfc-d6bd-4569-8b09-36dce65d017f">
   NmrProviderDetachClientComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568784">NmrRegisterProvider</a>



<a href="https://msdn.microsoft.com/0af476f6-0113-4aeb-b7d6-8e0e64a89bd0">
   ProviderCleanupBindingContext</a>



<a href="https://msdn.microsoft.com/0f29bf89-856c-4019-a966-3e666a7fc78d">ProviderDetachClient</a>
 

 

