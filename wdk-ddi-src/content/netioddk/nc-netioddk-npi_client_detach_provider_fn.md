---
UID: NC:netioddk.NPI_CLIENT_DETACH_PROVIDER_FN
title: NPI_CLIENT_DETACH_PROVIDER_FN
author: windows-driver-content
description: A client module's ClientDetachProvider callback function detaches the client module from a provider module.
old-location: netvista\clientdetachprovider.htm
tech.root: netvista
ms.assetid: a684136a-e2f2-4f82-9e9a-166b40bd7536
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: ClientDetachProvider, ClientDetachProvider callback function [Network Drivers Starting with Windows Vista], NPI_CLIENT_DETACH_PROVIDER_FN, NPI_CLIENT_DETACH_PROVIDER_FN callback, PNPI_CLIENT_DETACH_PROVIDER_FN, PNPI_CLIENT_DETACH_PROVIDER_FN callback function [Network Drivers Starting with Windows Vista], netioddk/ClientDetachProvider, netvista.clientdetachprovider, nmrref_5197d4f5-2cd0-4134-bccb-b509853718cd.xml
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
-	PNPI_CLIENT_DETACH_PROVIDER_FN
product:
- Windows
targetos: Windows
req.typenames: 
---

# NPI_CLIENT_DETACH_PROVIDER_FN callback function


## -description


A client module's 
  <i>ClientDetachProvider</i> callback function detaches the client module from a provider module.


## -parameters




### -param ClientBindingContext [in]

A pointer to the client module's context for the binding between the client module and the
     provider module from which it is detaching. The client module passes this pointer to the NMR when it
     calls the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568770">NmrClientAttachProvider</a> function
     to attach to the provider module.


## -returns



A client module's 
     <i>ClientDetachProvider</i> callback function returns one of the following NTSTATUS codes:

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
The client module successfully detached from the provider module.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The client module could not detach from the provider module immediately.

</td>
</tr>
</table>
 




## -remarks



The NMR calls a client module's 
    <i>ClientDetachProvider</i> callback function whenever the binding between the client module and a
    provider module needs to be terminated. Detachment is initiated by either the client module calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568774">NmrDeregisterClient</a> function or the
    provider module calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568778">NmrDeregisterProvider</a> function.

After its 
    <i>ClientDetachProvider</i> callback function has been called, a client module should not make any more
    calls to any of the provider module's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> functions. If there are no
    in-progress calls to any of the provider module's 
    NPI functions when the client
    module's 
    <i>ClientDetachProvider</i> callback function is called, the client module's 
    <i>ClientDetachProvider</i> callback function returns STATUS_SUCCESS.

If there are in-progress calls to one or more of the provider module's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> functions when the client
    module's 
    <i>ClientDetachProvider</i> callback function is called, then the client module's 
    <i>ClientDetachProvider</i> callback function returns STATUS_PENDING. In this situation, the client module
    must call the 
    <a href="https://msdn.microsoft.com/e54864de-9558-44b1-9c5a-0f2ecc6516b1">
    NmrClientDetachProviderComplete</a> function after all in-progress calls to the provider module's 
    NPI functions have completed. The
    call to the 
    <b>
    NmrClientDetachProviderComplete</b> function notifies the NMR that detachment from the provider module
    is complete.

The NMR calls the client module's 
    <a href="https://msdn.microsoft.com/eebffed4-a2e0-4743-871b-f50f0cdda30d">
    ClientCleanupBindingContext</a> callback function and the provider module's 
    <a href="https://msdn.microsoft.com/0af476f6-0113-4aeb-b7d6-8e0e64a89bd0">
    ProviderCleanupBindingContext</a> callback function after both the client module and the provider
    module have completed detachment from each other.

The NMR calls a client module's 
    <i>ClientDetachProvider</i> callback function at any IRQL &lt;= DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/eebffed4-a2e0-4743-871b-f50f0cdda30d">ClientCleanupBindingContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568812">NPI_CLIENT_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568770">NmrClientAttachProvider</a>



<a href="https://msdn.microsoft.com/e54864de-9558-44b1-9c5a-0f2ecc6516b1">
   NmrClientDetachProviderComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568774">NmrDeregisterClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568778">NmrDeregisterProvider</a>



<a href="https://msdn.microsoft.com/0af476f6-0113-4aeb-b7d6-8e0e64a89bd0">
   ProviderCleanupBindingContext</a>
 

 

