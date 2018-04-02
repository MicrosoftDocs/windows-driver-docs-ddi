---
UID: NS:netioddk._NPI_REGISTRATION_INSTANCE
title: "_NPI_REGISTRATION_INSTANCE"
author: windows-driver-content
description: The NPI_REGISTRATION_INSTANCE structure defines the data related to the registration of a network module with the NMR.
old-location: netvista\npi_registration_instance.htm
old-project: netvista
ms.assetid: a368f9d9-a7e0-4b35-ba14-b0919f74029d
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NPI_REGISTRATION_INSTANCE, NPI_REGISTRATION_INSTANCE structure [Network Drivers Starting with Windows Vista], PNPI_REGISTRATION_INSTANCE, PNPI_REGISTRATION_INSTANCE structure pointer [Network Drivers Starting with Windows Vista], _NPI_REGISTRATION_INSTANCE, netioddk/NPI_REGISTRATION_INSTANCE, netioddk/PNPI_REGISTRATION_INSTANCE, netvista.npi_registration_instance, nmrref_a31a8531-bab8-47d5-b79e-a239dcde475f.xml
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
-	NPI_REGISTRATION_INSTANCE
product: Windows
targetos: Windows
req.typenames: NPI_REGISTRATION_INSTANCE
---

# _NPI_REGISTRATION_INSTANCE structure


## -description


The NPI_REGISTRATION_INSTANCE structure defines the data related to the registration of a network
  module with the NMR.


## -struct-fields




### -field Version

The version of the NMR with which the network module is registering. A network module should set
     this member to zero.


### -field Size

The size, in bytes, of the NPI_REGISTRATION_INSTANCE structure.


### -field NpiId

A pointer to the 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> identifier for the specific 
     NPI to which the network module
     is registering as either a client or a provider. The NPIID data type is defined as:
     

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef GUID NPIID;
typedef CONST NPIID *PNPIID;</pre>
</td>
</tr>
</table></span></div>

### -field ModuleId

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568813">NPI_MODULEID</a> structure that uniquely
     identifies the network module.


### -field Number

The implementation number of the 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> for which the network module
     is registering as either a client or a provider. A network module can support multiple implementations
     of the same 
     NPI by registering as either a
     client or a provider of each implementation of the 
     NPI. If there is only one
     implementation of an 
     NPI, this member is set to
     zero.


### -field OPTIONAL

 




#### - NpiSpecificCharacteristics

A pointer to a structure that specifies characteristics that are unique to the network module. The
     contents of the structure are 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a>-specific. A network module
     should set this member to <b>NULL</b> if it is registering as a client of an NPI that does not define a client
     characteristics structure or if it is registering as a provider of an NPI that does not define a
     provider characteristics structure.


## -remarks



An NPI_REGISTRATION_INSTANCE structure is a member of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568812">NPI_CLIENT_CHARACTERISTICS</a> and 
    <a href="https://msdn.microsoft.com/a83220e8-496c-4b83-b774-88ab1f017e8d">
    NPI_PROVIDER_CHARACTERISTICS</a> structures. These structures are used for registering network modules
    with the NMR.

When the NMR calls a cleint module's 
    <a href="https://msdn.microsoft.com/8f8abdb1-d018-4404-a80a-74017c324a0f">ClientAttachProvider</a> callback
    function, it passes a pointer to the NPI_REGISTRATION_INSTANCE structure for the provider module to which
    the client module can attach itself. Likewise, when the NMR calls a provider module's 
    <a href="https://msdn.microsoft.com/6c8e6cf1-0528-4da2-acc1-81ec9dbc23c3">ProviderAttachClient</a> callback
    function, it passes a pointer to the NPI_REGISTRATION_INSTANCE structure for the client module to which
    the provider module can attach itself.

A network module must make sure that the memory for the NPIID pointed to by the 
    <b>NpiId</b> member, the memory for the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568813">NPI_MODULEID</a> structure pointed to by the 
    <b>ModuleId</b> member, and the memory for the 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a>-specific characteristics
    structure pointed to by the 
    <b>NpiSpecificCharacteristics</b> member remain valid and resident in memory as long as the network module
    is registered with the NMR.




## -see-also




<a href="https://msdn.microsoft.com/8f8abdb1-d018-4404-a80a-74017c324a0f">ClientAttachProvider</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568812">NPI_CLIENT_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568813">NPI_MODULEID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568814">NPI_PROVIDER_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/6c8e6cf1-0528-4da2-acc1-81ec9dbc23c3">ProviderAttachClient</a>
 

 

