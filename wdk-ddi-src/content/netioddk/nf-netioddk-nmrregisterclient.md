---
UID: NF:netioddk.NmrRegisterClient
title: NmrRegisterClient function
author: windows-driver-content
description: The NmrRegisterClient function registers a client module with the NMR.
old-location: netvista\nmrregisterclient.htm
old-project: netvista
ms.assetid: 9a8d2bc1-a75a-449d-8cfe-9d1f16a9dbb7
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NmrRegisterClient, NmrRegisterClient function [Network Drivers Starting with Windows Vista], netioddk/NmrRegisterClient, netvista.nmrregisterclient, nmrref_245036b1-3c92-46e6-bc7d-763e91e8b9f3.xml
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
-	NmrRegisterClient
product:
- Windows
targetos: Windows
req.typenames: NET_DMA_PROVIDER_CHARACTERISTICS, *PNET_DMA_PROVIDER_CHARACTERISTICS
---

# NmrRegisterClient function


## -description


The 
  <b>NmrRegisterClient</b> function registers a client module with the NMR.


## -parameters




### -param ClientCharacteristics [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/03d73a80-0860-4ec7-8eb1-5954f64b6026">
     NPI_CLIENT_CHARACTERISTICS</a> structure that describes the characteristics of the client module. The
     client module must make sure that this structure remains valid and resident in memory as long as the
     client module is registered with the NMR.


### -param ClientContext [in]

A pointer to a caller-supplied context for the registration. The client module uses this context
     to keep track of the state of the client registration. The contents of the client module's registration
     context are opaque to the NMR. The NMR passes this pointer to the client module whenever it calls the
     client module's 
     <a href="https://msdn.microsoft.com/8f8abdb1-d018-4404-a80a-74017c324a0f">ClientAttachProvider</a> callback
     function. The client module must make sure that its registration context remains valid and resident in
     memory as long as the client module is registered with the NMR.


### -param NmrClientHandle [out]

A pointer to a variable that receives a handle used by the NMR to represent the registration of
     the client module. The client module must save this handle and pass it as a parameter to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568774">NmrDeregisterClient</a> function when it
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
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> so that it can attach to
    provider modules that register as providers of the same 
    NPI.

A client module typically calls the 
    <b>NmrRegisterClient</b> function from its 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function after it has completed
    all other initialization tasks. The call to the 
    <b>NmrRegisterClient</b> function indicates to the NMR that the client module is ready to attach to any
    provider modules that have registered or will register as providers of the same 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> for which the client module
    has registered as a client.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568812">NPI_CLIENT_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568774">NmrDeregisterClient</a>
 

 

