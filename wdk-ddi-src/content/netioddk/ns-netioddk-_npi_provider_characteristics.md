---
UID: NS:netioddk._NPI_PROVIDER_CHARACTERISTICS
title: "_NPI_PROVIDER_CHARACTERISTICS" (netioddk.h)
description: The NPI_PROVIDER_CHARACTERISTICS structure defines the characteristics of a provider module.
old-location: netvista\npi_provider_characteristics.htm
tech.root: netvista
ms.assetid: a83220e8-496c-4b83-b774-88ab1f017e8d
ms.date: 05/02/2018
ms.keywords: NPI_PROVIDER_CHARACTERISTICS, NPI_PROVIDER_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNPI_PROVIDER_CHARACTERISTICS, PNPI_PROVIDER_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NPI_PROVIDER_CHARACTERISTICS, netioddk/NPI_PROVIDER_CHARACTERISTICS, netioddk/PNPI_PROVIDER_CHARACTERISTICS, netvista.npi_provider_characteristics, nmrref_ceebed62-8102-41e3-af13-e663c1e8babb.xml
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	netioddk.h
api_name:
-	NPI_PROVIDER_CHARACTERISTICS
product:
- Windows
targetos: Windows
req.typenames: NPI_PROVIDER_CHARACTERISTICS
---

# _NPI_PROVIDER_CHARACTERISTICS structure


## -description


The NPI_PROVIDER_CHARACTERISTICS structure defines the characteristics of a provider module.


## -struct-fields




### -field Version

The version of the NMR with which the provider is registering. A provider module should set this
     member to zero.


### -field Length

The size, in bytes, of the NPI_PROVIDER_CHARACTERISTICS structure.


### -field ProviderAttachClient

A pointer to the provider module's 
     <a href="https://msdn.microsoft.com/6c8e6cf1-0528-4da2-acc1-81ec9dbc23c3">ProviderAttachClient</a> callback
     function.


### -field ProviderDetachClient

A pointer to the provider module's 
     <a href="https://msdn.microsoft.com/0f29bf89-856c-4019-a966-3e666a7fc78d">ProviderDetachClient</a> callback
     function.


### -field ProviderCleanupBindingContext

A pointer to the provider module's 
     <a href="https://msdn.microsoft.com/0af476f6-0113-4aeb-b7d6-8e0e64a89bd0">
     ProviderCleanupBindingContext</a> callback function. If the provider module does not dynamically
     allocate the memory for its binding context and no other cleanup of its binding context is required,
     then the provider module does not need to implement a 
     <i>
     ProviderCleanupBindingContext</i> callback function. If the provider module does not implement a 
     <i>
     ProviderCleanupBindingContext</i> callback function, then this member must be set to <b>NULL</b>.


### -field ProviderRegistrationInstance

An 
     <a href="https://msdn.microsoft.com/a368f9d9-a7e0-4b35-ba14-b0919f74029d">
     NPI_REGISTRATION_INSTANCE</a> structure that specifies the identity of the provider module and the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> for which it is
     registering.


## -remarks



A provider module passes a pointer to an NPI_PROVIDER_CHARACTERISTICS structure to the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568784">NmrRegisterProvider</a> function when it
    registers itself with the NMR.

A provider module must make sure that this structure remains valid and resident in memory as long as
    the provider module is registered with the NMR.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568815">NPI_REGISTRATION_INSTANCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568784">NmrRegisterProvider</a>



<a href="https://msdn.microsoft.com/6c8e6cf1-0528-4da2-acc1-81ec9dbc23c3">ProviderAttachClient</a>



<a href="https://msdn.microsoft.com/0af476f6-0113-4aeb-b7d6-8e0e64a89bd0">
   ProviderCleanupBindingContext</a>



<a href="https://msdn.microsoft.com/0f29bf89-856c-4019-a966-3e666a7fc78d">ProviderDetachClient</a>
 

 

