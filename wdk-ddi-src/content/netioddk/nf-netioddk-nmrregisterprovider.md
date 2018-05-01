---
UID: NF:netioddk.NmrRegisterProvider
title: NmrRegisterProvider function
author: windows-driver-content
description: The NmrRegisterProvider function registers a provider module with the NMR.
old-location: netvista\nmrregisterprovider.htm
old-project: netvista
ms.assetid: aac9382c-5177-4216-bf3d-7970b18662eb
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NmrRegisterProvider, NmrRegisterProvider function [Network Drivers Starting with Windows Vista], netioddk/NmrRegisterProvider, netvista.nmrregisterprovider, nmrref_ad505c0b-91dd-413d-be24-ab331f8eadca.xml
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Netio.lib
-	Netio.dll
api_name:
-	NmrRegisterProvider
product: Windows
targetos: Windows
req.typenames: 
---

# NmrRegisterProvider function


## -description


The 
  <b>NmrRegisterProvider</b> function registers a provider module with the NMR.


## -parameters




### -param ProviderCharacteristics [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/a83220e8-496c-4b83-b774-88ab1f017e8d">
     NPI_PROVIDER_CHARACTERISTICS</a> structure that describes the characteristics of the provider module.
     The provider module must make sure that this structure remains valid and resident in memory as long as
     the provider module is registered with the NMR.


### -param ProviderContext [in]

A pointer to a caller-supplied context for the registration. The provider module uses this context
     to keep track of the state of the provider registration. The contents of the provider module's
     registration context are opaque to the NMR. The NMR passes this pointer to the provider module whenever
     it calls the provider module's 
     <a href="https://msdn.microsoft.com/6c8e6cf1-0528-4da2-acc1-81ec9dbc23c3">ProviderAttachClient</a> callback
     function. The provider module must make sure that this context remains valid and resident in memory as
     long as the provider module is registered with the NMR.


### -param NmrProviderHandle [out]

A pointer to a variable that receives a handle used by the NMR to represent the registration of
     the provider module. The provider module must save this handle and pass it as a parameter to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568778">NmrDeregisterProvider</a> function when
     it deregisters from the NMR.


## -returns



The 
     <b>NmrRegisterProvider</b> function returns one of the following NTSTATUS codes:

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
The NMR successfully registered the provider module.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The NMR did not have sufficient system resources to register the provider module.

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



A provider module calls the 
    <b>NmrRegisterProvider</b> function to register as a provider of an 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> so that it can attach to
    client modules that register as clients of the same 
    NPI.

A provider module typically calls the 
    <b>NmrRegisterProvider</b> function from its 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function after it has completed
    all other initialization tasks. The call to the 
    <b>NmrRegisterProvider</b> function indicates to the NMR that the provider module is ready to attach to
    any client modules that have registered or will register as clients of the same 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> for which the provider module
    has registered as a provider.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568814">NPI_PROVIDER_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568778">NmrDeregisterProvider</a>
 

 

