---
UID: NS:ndischimney._NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
title: "_NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS"
author: windows-driver-content
description: The NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure specifies a protocol driver's generic chimney offload entry points.
old-location: netvista\ndis_client_chimney_offload_generic_characteristics.htm
tech.root: netvista
ms.assetid: 66eb9528-e026-44cd-a775-c8d963036adc
ms.date: 05/02/2018
ms.keywords: "*PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, ndischimney/NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, ndischimney/PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, netvista.ndis_client_chimney_offload_generic_characteristics, tcp_chim_struct_5db55d5e-f540-4f60-9f3b-adcd24932b1d.xml"
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
-	NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
product:
- Windows
targetos: Windows
req.typenames: NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, *PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
---

# _NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure specifies a protocol driver's
  generic chimney offload entry points. Generic chimney offload entry points apply to all chimney offload
  types. Currently, TCP chimney offload is the only defined chimney offload type.


## -struct-fields




### -field Header

The header of the NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure. The header is
     formatted as an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure. The
     NDIS_OBJECT_HEADER structure contains the revision number of the
     NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure and the size of the
     NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure, including the header, in bytes. The 
     <b>Type</b> member of the header is not significant.


### -field Flags

Reserved for system use.


### -field InitiateOffloadCompleteHandler

Specifies the entry point of the driver's 
     <a href="https://msdn.microsoft.com/0300d841-b211-42f8-b60d-d7d37201e778">
     ProtocolInitiateOffloadComplete</a> function.


### -field TerminateOffloadCompleteHandler

The entry point of the driver's 
     <a href="https://msdn.microsoft.com/614d36e8-38ac-49a7-8711-7a6c6646309c">
     ProtocolTerminateOffloadComplete</a> function.


### -field UpdateOffloadCompleteHandler

The entry point of the driver's 
     <a href="https://msdn.microsoft.com/3cd7a32a-d560-429b-b191-aeabb87433f3">
     ProtocolUpdateOffloadComplete</a> function.


### -field InvalidateOffloadCompleteHandler

The entry point of the driver's 
     <a href="https://msdn.microsoft.com/6d2c71d0-9686-4eb5-9715-27de3dc8b390">
     ProtocolInvalidateOffloadComplete</a> function.


### -field QueryOffloadCompleteHandler

The entry point of the driver's 
     <a href="https://msdn.microsoft.com/f521af88-eb96-4077-8882-9b1d02c6c87c">
     ProtocolQueryOffloadComplete</a> function.


### -field IndicateOffloadEventHandler

The entry point of the driver's 
     <a href="https://msdn.microsoft.com/608c1c7c-1eb3-4d86-9471-313fce2df00e">
     ProtocolIndicateOffloadEvent</a> function.


## -remarks



To register its generic chimney offload entry points, a protocol or intermediate driver calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a> function
    in the context of the 
    <a href="https://msdn.microsoft.com/342e23ad-d38b-4100-949a-220b8fbdcf6e">ProtocolSetOptions</a> function. To the 
    <b>NdisSetOptionalHandlers</b> function,
    the protocol or intermediate driver passes a pointer to the
    NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>



<a href="https://msdn.microsoft.com/608c1c7c-1eb3-4d86-9471-313fce2df00e">
   ProtocolIndicateOffloadEvent</a>



<a href="https://msdn.microsoft.com/0300d841-b211-42f8-b60d-d7d37201e778">
   ProtocolInitiateOffloadComplete</a>



<a href="https://msdn.microsoft.com/6d2c71d0-9686-4eb5-9715-27de3dc8b390">
   ProtocolInvalidateOffloadComplete</a>



<a href="https://msdn.microsoft.com/f521af88-eb96-4077-8882-9b1d02c6c87c">
   ProtocolQueryOffloadComplete</a>



<a href="https://msdn.microsoft.com/342e23ad-d38b-4100-949a-220b8fbdcf6e">ProtocolSetOptions</a>



<a href="https://msdn.microsoft.com/614d36e8-38ac-49a7-8711-7a6c6646309c">
   ProtocolTerminateOffloadComplete</a>



<a href="https://msdn.microsoft.com/3cd7a32a-d560-429b-b191-aeabb87433f3">
   ProtocolUpdateOffloadComplete</a>
 

 

