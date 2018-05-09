---
UID: NC:netioddk.NPI_PROVIDER_DETACH_CLIENT_FN
title: NPI_PROVIDER_DETACH_CLIENT_FN
author: windows-driver-content
description: A provider module's ProviderDetachClient callback function detaches the provider module from a client module.
old-location: netvista\providerdetachclient.htm
old-project: netvista
ms.assetid: 0f29bf89-856c-4019-a966-3e666a7fc78d
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NPI_PROVIDER_DETACH_CLIENT_FN, NPI_PROVIDER_DETACH_CLIENT_FN callback, PNPI_PROVIDER_DETACH_CLIENT_FN, PNPI_PROVIDER_DETACH_CLIENT_FN callback function [Network Drivers Starting with Windows Vista], ProviderDetachClient, ProviderDetachClient callback function [Network Drivers Starting with Windows Vista], netioddk/ProviderDetachClient, netvista.providerdetachclient, nmrref_04fc189d-40e1-4cc5-87ea-dda2664f7e63.xml
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
-	PNPI_PROVIDER_DETACH_CLIENT_FN
product:
- Windows
targetos: Windows
req.typenames: 
---

# NPI_PROVIDER_DETACH_CLIENT_FN callback function


## -description


A provider module's 
  <i>ProviderDetachClient</i> callback function detaches the provider module from a client module.


## -parameters




### -param ProviderBindingContext [in]

A pointer to the provider module's context for the binding between the provider module and the
     client module from which it is detaching. The provider module's 
     <a href="https://msdn.microsoft.com/6c8e6cf1-0528-4da2-acc1-81ec9dbc23c3">ProviderAttachClient</a> callback
     function returns this pointer to the NMR when it attaches to the client module.


## -returns



A provider module's 
     <i>ProviderDetachClient</i> callback function returns one of the following NTSTATUS codes:

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
The provider module successfully detached from the client module.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The provider module could not detach from the client module immediately.

</td>
</tr>
</table>
 




## -remarks



The NMR calls a provider module's 
    <i>ProviderDetachClient</i> callback function whenever the binding between the provider module and a
    client module needs to be terminated. Detachment is initiated by either the client module calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568774">NmrDeregisterClient</a> function or the
    provider module calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568778">NmrDeregisterProvider</a> function.

After its 
    <i>ProviderDetachClient</i> callback function has been called, a provider module should not make any more
    calls to any of the client module's 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> callback functions. If there
    are no in-progress calls to any of the client module's 
    NPI callback functions when the
    provider module's 
    <i>ProviderDetachClient</i> callback function is called, then the provider module's 
    <i>ProviderDetachClient</i> callback function returns STATUS_SUCCESS.

If there are in-progress calls to one or more of the client module's 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> callback functions when the
    provider module's 
    <i>ProviderDetachClient</i> callback function is called, the provider module's 
    <i>ProviderDetachClient</i> callback function returns STATUS_PENDING. In this situation, the provider
    module must call the 
    <a href="https://msdn.microsoft.com/a52b3cfc-d6bd-4569-8b09-36dce65d017f">
    NmrProviderDetachClientComplete</a> function after all in-progress calls to the client module's 
    NPI callback functions have
    completed. The call to the 
    <b>
    NmrProviderDetachClientComplete</b> function notifies the NMR that detachment from the client module is
    complete.

The NMR calls the client module's 
    <a href="https://msdn.microsoft.com/eebffed4-a2e0-4743-871b-f50f0cdda30d">
    ClientCleanupBindingContext</a> callback function and the provider module's 
    <a href="https://msdn.microsoft.com/0af476f6-0113-4aeb-b7d6-8e0e64a89bd0">
    ProviderCleanupBindingContext</a> callback function after both the client module and the provider
    module have completed detaching from each other.

The NMR calls a provider module's 
    <i>ProviderDetachClient</i> callback function at any IRQL &lt;= DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/eebffed4-a2e0-4743-871b-f50f0cdda30d">ClientCleanupBindingContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568814">NPI_PROVIDER_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568774">NmrDeregisterClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568778">NmrDeregisterProvider</a>



<a href="https://msdn.microsoft.com/a52b3cfc-d6bd-4569-8b09-36dce65d017f">
   NmrProviderDetachClientComplete</a>



<a href="https://msdn.microsoft.com/6c8e6cf1-0528-4da2-acc1-81ec9dbc23c3">ProviderAttachClient</a>



<a href="https://msdn.microsoft.com/0af476f6-0113-4aeb-b7d6-8e0e64a89bd0">
   ProviderCleanupBindingContext</a>
 

 

