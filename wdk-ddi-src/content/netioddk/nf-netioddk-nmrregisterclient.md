---
UID: NF:netioddk.NmrRegisterClient
title: NmrRegisterClient function
author: windows-driver-content
description: The NmrRegisterClient function registers a client module with the NMR.
old-location: netvista\nmrregisterclient.htm
old-project: netvista
ms.assetid: 9a8d2bc1-a75a-449d-8cfe-9d1f16a9dbb7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NmrRegisterClient
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
req.alt-api: NmrRegisterClient
req.alt-loc: Netio.lib,Netio.dll
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
req.typenames: *PNET_DMA_PROVIDER_CHARACTERISTICS, NET_DMA_PROVIDER_CHARACTERISTICS
---

# NmrRegisterClient function



## -description
The 
  <b>NmrRegisterClient</b> function registers a client module with the NMR.



## -syntax

````
NTSTATUS NmrRegisterClient(
  _In_  PNPI_CLIENT_CHARACTERISTICS ClientCharacteristics,
  _In_  PVOID                       ClientContext,
  _Out_ PHANDLE                     NmrClientHandle
);
````


## -parameters

### -param ClientCharacteristics [in]

A pointer to an 
     <a href="..\netioddk\ns-netioddk-_npi_client_characteristics.md">
     NPI_CLIENT_CHARACTERISTICS</a> structure that describes the characteristics of the client module. The
     client module must make sure that this structure remains valid and resident in memory as long as the
     client module is registered with the NMR.


### -param ClientContext [in]

A pointer to a caller-supplied context for the registration. The client module uses this context
     to keep track of the state of the client registration. The contents of the client module's registration
     context are opaque to the NMR. The NMR passes this pointer to the client module whenever it calls the
     client module's 
     <a href="..\netioddk\nc-netioddk-npi_client_attach_provider_fn.md">ClientAttachProvider</a> callback
     function. The client module must make sure that its registration context remains valid and resident in
     memory as long as the client module is registered with the NMR.


### -param NmrClientHandle [out]

A pointer to a variable that receives a handle used by the NMR to represent the registration of
     the client module. The client module must save this handle and pass it as a parameter to the 
     <a href="..\netioddk\nf-netioddk-nmrderegisterclient.md">NmrDeregisterClient</a> function when it
     deregisters from the NMR.


## -returns
The 
     <b>NmrRegisterClient</b> function returns one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The NMR successfully registered the client module.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The NMR did not have sufficient system resources to register the client module.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 


## -remarks
A client module calls the 
    <b>NmrRegisterClient</b> function to register as a client of an 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> so that it can attach to
    provider modules that register as providers of the same 
    NPI.

A client module typically calls the 
    <b>NmrRegisterClient</b> function from its 
    <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> function after it has completed
    all other initialization tasks. The call to the 
    <b>NmrRegisterClient</b> function indicates to the NMR that the client module is ready to attach to any
    provider modules that have registered or will register as providers of the same 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> for which the client module
    has registered as a client.


## -see-also
<dl>
<dt>
<a href="..\netioddk\nf-netioddk-nmrderegisterclient.md">NmrDeregisterClient</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a>
</dt>
<dt>
<a href="..\netioddk\ns-netioddk-_npi_client_characteristics.md">NPI_CLIENT_CHARACTERISTICS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NmrRegisterClient function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

