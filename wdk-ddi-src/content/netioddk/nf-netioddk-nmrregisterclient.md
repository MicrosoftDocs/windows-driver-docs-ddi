---
UID: NF:netioddk.NmrRegisterClient
title: NmrRegisterClient function (netioddk.h)
description: The NmrRegisterClient function registers a client module with the NMR.
old-location: netvista\nmrregisterclient.htm
tech.root: netvista
ms.assetid: 9a8d2bc1-a75a-449d-8cfe-9d1f16a9dbb7
ms.date: 05/02/2018
keywords: ["NmrRegisterClient function"]
ms.keywords: NmrRegisterClient, NmrRegisterClient function [Network Drivers Starting with Windows Vista], netioddk/NmrRegisterClient, netvista.nmrregisterclient, nmrref_245036b1-3c92-46e6-bc7d-763e91e8b9f3.xml
f1_keywords:
 - "netioddk/NmrRegisterClient"
 - "NmrRegisterClient"
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
- Netio.lib
- Netio.dll
api_name:
- NmrRegisterClient
targetos: Windows
req.typenames: 
---

# NmrRegisterClient function


## -description


The 
  <b>NmrRegisterClient</b> function registers a client module with the NMR.


## -parameters




### -param ClientCharacteristics 
[in]
A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/ns-netioddk-_npi_client_characteristics">
     NPI_CLIENT_CHARACTERISTICS</a> structure that describes the characteristics of the client module. The
     client module must make sure that this structure remains valid and resident in memory as long as the
     client module is registered with the NMR.


### -param ClientContext 
[in]
A pointer to a caller-supplied context for the registration. The client module uses this context
     to keep track of the state of the client registration. The contents of the client module's registration
     context are opaque to the NMR. The NMR passes this pointer to the client module whenever it calls the
     client module's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_client_attach_provider_fn">ClientAttachProvider</a> callback
     function. The client module must make sure that its registration context remains valid and resident in
     memory as long as the client module is registered with the NMR.


### -param NmrClientHandle 
[out]
A pointer to a variable that receives a handle used by the NMR to represent the registration of
     the client module. The client module must save this handle and pass it as a parameter to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nf-netioddk-nmrderegisterclient">NmrDeregisterClient</a> function when it
     deregisters from the NMR.


## -returns



The 
     <b>NmrRegisterClient</b> function returns one of the following NTSTATUS codes:

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
The NMR successfully registered the client module.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The NMR did not have sufficient system resources to register the client module.

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
    <b>NmrRegisterClient</b> function to register as a client of an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> so that it can attach to
    provider modules that register as providers of the same 
    NPI.

A client module typically calls the 
    <b>NmrRegisterClient</b> function from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> function after it has completed
    all other initialization tasks. The call to the 
    <b>NmrRegisterClient</b> function indicates to the NMR that the client module is ready to attach to any
    provider modules that have registered or will register as providers of the same 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> for which the client module
    has registered as a client.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/ns-netioddk-_npi_client_characteristics">NPI_CLIENT_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nf-netioddk-nmrderegisterclient">NmrDeregisterClient</a>
 

 

