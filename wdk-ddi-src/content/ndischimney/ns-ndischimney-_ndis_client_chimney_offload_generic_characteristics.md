---
UID: NS:ndischimney._NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
title: _NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS (ndischimney.h)
description: The NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure specifies a protocol driver's generic chimney offload entry points.
old-location: netvista\ndis_client_chimney_offload_generic_characteristics.htm
tech.root: netvista
ms.assetid: 66eb9528-e026-44cd-a775-c8d963036adc
ms.date: 05/02/2018
ms.keywords: "*PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, ndischimney/NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, ndischimney/PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, netvista.ndis_client_chimney_offload_generic_characteristics, tcp_chim_struct_5db55d5e-f540-4f60-9f3b-adcd24932b1d.xml"
ms.topic: struct
f1_keywords:
 - "ndischimney/NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndischimney.h
api_name:
- NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
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
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure. The
     NDIS_OBJECT_HEADER structure contains the revision number of the
     NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure and the size of the
     NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure, including the header, in bytes. The 
     <b>Type</b> member of the header is not significant.


### -field Flags

Reserved for system use.


### -field InitiateOffloadCompleteHandler

Specifies the entry point of the driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-initiate_offload_complete_handler">
     ProtocolInitiateOffloadComplete</a> function.


### -field TerminateOffloadCompleteHandler

The entry point of the driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-terminate_offload_complete_handler">
     ProtocolTerminateOffloadComplete</a> function.


### -field UpdateOffloadCompleteHandler

The entry point of the driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-update_offload_complete_handler">
     ProtocolUpdateOffloadComplete</a> function.


### -field InvalidateOffloadCompleteHandler

The entry point of the driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-invalidate_offload_complete_handler">
     ProtocolInvalidateOffloadComplete</a> function.


### -field QueryOffloadCompleteHandler

The entry point of the driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-query_offload_complete_handler">
     ProtocolQueryOffloadComplete</a> function.


### -field IndicateOffloadEventHandler

The entry point of the driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-indicate_offload_event_handler">
     ProtocolIndicateOffloadEvent</a> function.


## -remarks



To register its generic chimney offload entry points, a protocol or intermediate driver calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a> function
    in the context of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-set_options">ProtocolSetOptions</a> function. To the 
    <b>NdisSetOptionalHandlers</b> function,
    the protocol or intermediate driver passes a pointer to the
    NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-indicate_offload_event_handler">
   ProtocolIndicateOffloadEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-initiate_offload_complete_handler">
   ProtocolInitiateOffloadComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-invalidate_offload_complete_handler">
   ProtocolInvalidateOffloadComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-query_offload_complete_handler">
   ProtocolQueryOffloadComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-set_options">ProtocolSetOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-terminate_offload_complete_handler">
   ProtocolTerminateOffloadComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-update_offload_complete_handler">
   ProtocolUpdateOffloadComplete</a>
 

 

