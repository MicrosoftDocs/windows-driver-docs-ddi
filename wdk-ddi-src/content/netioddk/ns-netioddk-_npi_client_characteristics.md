---
UID: NS:netioddk._NPI_CLIENT_CHARACTERISTICS
title: "_NPI_CLIENT_CHARACTERISTICS"
author: windows-driver-content
description: The NPI_CLIENT_CHARACTERISTICS structure defines the characteristics of a client module.
old-location: netvista\npi_client_characteristics.htm
old-project: netvista
ms.assetid: 03d73a80-0860-4ec7-8eb1-5954f64b6026
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NPI_CLIENT_CHARACTERISTICS, NPI_CLIENT_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNPI_CLIENT_CHARACTERISTICS, PNPI_CLIENT_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NPI_CLIENT_CHARACTERISTICS, netioddk/NPI_CLIENT_CHARACTERISTICS, netioddk/PNPI_CLIENT_CHARACTERISTICS, netvista.npi_client_characteristics, nmrref_01bb300c-5e76-40e3-9358-a01e991ceecf.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	netioddk.h
api_name:
-	NPI_CLIENT_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: NPI_CLIENT_CHARACTERISTICS
---

# _NPI_CLIENT_CHARACTERISTICS structure


## -description


The NPI_CLIENT_CHARACTERISTICS structure defines the characteristics of a client module.


## -syntax


````
typedef struct _NPI_CLIENT_CHARACTERISTICS {
  USHORT                                 Version;
  USHORT                                 Length;
  PNPI_CLIENT_ATTACH_PROVIDER_FN         ClientAttachProvider;
  PNPI_CLIENT_DETACH_PROVIDER_FN         ClientDetachProvider;
  PNPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN ClientCleanupBindingContext;
  NPI_REGISTRATION_INSTANCE              ClientRegistrationInstance;
} NPI_CLIENT_CHARACTERISTICS, *PNPI_CLIENT_CHARACTERISTICS;
````


## -struct-fields




### -field Version

The version of the NMR with which the client is registering. A client module should set this
     member to zero.


### -field Length

The size, in bytes, of the NPI_CLIENT_CHARACTERISTICS structure.


### -field ClientAttachProvider

A pointer to the client module's 
     <a href="..\netioddk\nc-netioddk-npi_client_attach_provider_fn.md">ClientAttachProvider</a> callback
     function.


### -field ClientDetachProvider

A pointer to the client module's 
     <a href="..\netioddk\nc-netioddk-npi_client_detach_provider_fn.md">ClientDetachProvider</a> callback
     function.


### -field ClientCleanupBindingContext

A pointer to the client module's 
     <a href="..\netioddk\nc-netioddk-npi_client_cleanup_binding_context_fn.md">
     ClientCleanupBindingContext</a> callback function. If the client module does not dynamically allocate
     the memory for its binding context and no other cleanup of its binding context is required, then the
     client module does not need to implement a 
     <i>
     ClientCleanupBindingContext</i> callback function. If the client module does not implement a 
     <i>
     ClientCleanupBindingContext</i> callback function, then this member must be set to <b>NULL</b>.


### -field ClientRegistrationInstance

An 
     <a href="..\netioddk\ns-netioddk-_npi_registration_instance.md">
     NPI_REGISTRATION_INSTANCE</a> structure that specifies the identity of the client module and the 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> for which it is
     registering.


## -remarks



A client module passes a pointer to an NPI_CLIENT_CHARACTERISTICS structure to the 
    <a href="..\netioddk\nf-netioddk-nmrregisterclient.md">NmrRegisterClient</a> function when it
    registers itself with the NMR.

A client module must make sure that this structure remains valid and resident in memory as long as the
    client module is registered with the NMR.




## -see-also

<a href="..\netioddk\nc-netioddk-npi_client_attach_provider_fn.md">ClientAttachProvider</a>



<a href="..\netioddk\nc-netioddk-npi_client_detach_provider_fn.md">ClientDetachProvider</a>



<a href="..\netioddk\nc-netioddk-npi_client_cleanup_binding_context_fn.md">ClientCleanupBindingContext</a>



<a href="..\netioddk\nf-netioddk-nmrregisterclient.md">NmrRegisterClient</a>



<a href="..\netioddk\ns-netioddk-_npi_registration_instance.md">NPI_REGISTRATION_INSTANCE</a>



 

 


