---
UID: NS:ndischimney._NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
title: "_NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS"
author: windows-driver-content
description: The NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure specifies the generic chimney offload miniport entry points of an offload target or intermediate driver.
old-location: netvista\ndis_provider_chimney_offload_generic_characteristics.htm
old-project: netvista
ms.assetid: e80a9999-2e4e-4da0-8aae-54ee71d9249d
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PNDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, PNDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, ndischimney/NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, ndischimney/PNDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, netvista.ndis_provider_chimney_offload_generic_characteristics, tcp_chim_struct_3145314d-c0a6-4d4e-b489-c38dda6c43e5.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	ndischimney.h
api_name:
-	NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, *PNDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
---

# _NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure specifies the generic chimney
  offload miniport entry points of an offload target or intermediate driver. Generic chimney offload entry
  points pertain to all chimney offload types. Currently, TCP chimney offload is the only defined chimney
  offload type.


## -struct-fields




### -field Header

The header of the NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure. The header is
     formatted as an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure. The
     NDIS_OBJECT_HEADER structure contains the revision number of the
     NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure and the size of the
     NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure, including the header, in bytes. The 
     <b>Type</b> member of the header is not significant.


### -field Flags

Reserved for system use.


### -field InitiateOffloadHandler

The entry point of the driver's 
     <a href="https://msdn.microsoft.com/f430642b-01bf-4ed7-bfea-e8dd8d5a8208">
     MiniportInitiateOffload</a> function.


### -field TerminateOffloadHandler

The entry point of the driver's 
     <a href="https://msdn.microsoft.com/1b808e3c-2d64-44c9-88d3-0a0311e1dc99">
     MiniportTerminateOffload</a> function.


### -field UpdateOffloadHandler

The entry point of the driver's 
     <a href="https://msdn.microsoft.com/b98b2e21-8b28-4da0-9cc9-6fa8cb6e5be7">
     MiniportUpdateOffload</a> function.


### -field InvalidateOffloadHandler

The entry point of the driver's 
     <a href="https://msdn.microsoft.com/58226149-daea-40aa-afb6-13ce615434b3">
     MiniportInvalidateOffload</a> function.


### -field QueryOffloadHandler

The entry point of the driver's 
     <a href="https://msdn.microsoft.com/a583c4cb-53c1-4eff-bcfe-c962f736b1f8">
     MiniportQueryOffload</a> function.


## -remarks



To register its generic chimney offload entry points, an offload target or intermediate driver calls
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a> function
    in the context of the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a> function. To the 
    <b>NdisSetOptionalHandlers</b> function, the offload target or intermediate driver passes a pointer to the
    NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure.




## -see-also




<a href="https://msdn.microsoft.com/f430642b-01bf-4ed7-bfea-e8dd8d5a8208">MiniportInitiateOffload</a>



<a href="https://msdn.microsoft.com/58226149-daea-40aa-afb6-13ce615434b3">MiniportInvalidateOffload</a>



<a href="https://msdn.microsoft.com/a583c4cb-53c1-4eff-bcfe-c962f736b1f8">MiniportQueryOffload</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a>



<a href="https://msdn.microsoft.com/1b808e3c-2d64-44c9-88d3-0a0311e1dc99">MiniportTerminateOffload</a>



<a href="https://msdn.microsoft.com/b98b2e21-8b28-4da0-9cc9-6fa8cb6e5be7">MiniportUpdateOffload</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>
 

 

