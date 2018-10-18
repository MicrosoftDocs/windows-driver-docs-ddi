---
UID: NS:netioddk._NPI_CLIENT_CHARACTERISTICS
title: "_NPI_CLIENT_CHARACTERISTICS"
author: windows-driver-content
description: The NPI_CLIENT_CHARACTERISTICS structure defines the characteristics of a client module.
old-location: netvista\npi_client_characteristics.htm
tech.root: netvista
ms.assetid: 03d73a80-0860-4ec7-8eb1-5954f64b6026
ms.date: 5/2/2018
ms.keywords: NPI_CLIENT_CHARACTERISTICS, NPI_CLIENT_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNPI_CLIENT_CHARACTERISTICS, PNPI_CLIENT_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NPI_CLIENT_CHARACTERISTICS, netioddk/NPI_CLIENT_CHARACTERISTICS, netioddk/PNPI_CLIENT_CHARACTERISTICS, netvista.npi_client_characteristics, nmrref_01bb300c-5e76-40e3-9358-a01e991ceecf.xml
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
-	NPI_CLIENT_CHARACTERISTICS
product:
- Windows
targetos: Windows
req.typenames: NPI_CLIENT_CHARACTERISTICS
---

# _NPI_CLIENT_CHARACTERISTICS structure


## -description


The NPI_CLIENT_CHARACTERISTICS structure defines the characteristics of a client module.


## -struct-fields




### -field Version

The version of the NMR with which the client is registering. A client module should set this
     member to zero.


### -field Length

The size, in bytes, of the NPI_CLIENT_CHARACTERISTICS structure.


### -field ClientAttachProvider

A pointer to the client module's 
     <a href="https://msdn.microsoft.com/8f8abdb1-d018-4404-a80a-74017c324a0f">ClientAttachProvider</a> callback
     function.


### -field ClientDetachProvider

A pointer to the client module's 
     <a href="https://msdn.microsoft.com/a684136a-e2f2-4f82-9e9a-166b40bd7536">ClientDetachProvider</a> callback
     function.


### -field ClientCleanupBindingContext

A pointer to the client module's 
     <a href="https://msdn.microsoft.com/eebffed4-a2e0-4743-871b-f50f0cdda30d">
     ClientCleanupBindingContext</a> callback function. If the client module does not dynamically allocate
     the memory for its binding context and no other cleanup of its binding context is required, then the
     client module does not need to implement a 
     <i>
     ClientCleanupBindingContext</i> callback function. If the client module does not implement a 
     <i>
     ClientCleanupBindingContext</i> callback function, then this member must be set to <b>NULL</b>.


### -field ClientRegistrationInstance

An 
     <a href="https://msdn.microsoft.com/a368f9d9-a7e0-4b35-ba14-b0919f74029d">
     NPI_REGISTRATION_INSTANCE</a> structure that specifies the identity of the client module and the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> for which it is
     registering.


## -remarks



A client module passes a pointer to an NPI_CLIENT_CHARACTERISTICS structure to the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568782">NmrRegisterClient</a> function when it
    registers itself with the NMR.

A client module must make sure that this structure remains valid and resident in memory as long as the
    client module is registered with the NMR.




## -see-also




<a href="https://msdn.microsoft.com/8f8abdb1-d018-4404-a80a-74017c324a0f">ClientAttachProvider</a>



<a href="https://msdn.microsoft.com/eebffed4-a2e0-4743-871b-f50f0cdda30d">ClientCleanupBindingContext</a>



<a href="https://msdn.microsoft.com/a684136a-e2f2-4f82-9e9a-166b40bd7536">ClientDetachProvider</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568815">NPI_REGISTRATION_INSTANCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568782">NmrRegisterClient</a>
 

 

