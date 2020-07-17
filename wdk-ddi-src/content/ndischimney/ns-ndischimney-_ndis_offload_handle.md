---
UID: NS:ndischimney._NDIS_OFFLOAD_HANDLE
title: _NDIS_OFFLOAD_HANDLE (ndischimney.h)
description: The NDIS_OFFLOAD_HANDLE structure represents a driver's context for an offloaded state object.
old-location: netvista\ndis_offload_handle.htm
tech.root: netvista
ms.assetid: cc1d7ca2-273a-42ca-896c-aebee862a4cd
ms.date: 05/02/2018
keywords: ["_NDIS_OFFLOAD_HANDLE structure"]
ms.keywords: "*PNDIS_OFFLOAD_HANDLE, NDIS_OFFLOAD_HANDLE, NDIS_OFFLOAD_HANDLE structure [Network Drivers Starting with Windows Vista], PNDIS_OFFLOAD_HANDLE, PNDIS_OFFLOAD_HANDLE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_OFFLOAD_HANDLE, ndischimney/NDIS_OFFLOAD_HANDLE, ndischimney/PNDIS_OFFLOAD_HANDLE, netvista.ndis_offload_handle, tcp_chim_struct_32ac0fbc-873b-4cd9-9121-d7e77667f05d.xml"
f1_keywords:
 - "ndischimney/NDIS_OFFLOAD_HANDLE"
 - "NDIS_OFFLOAD_HANDLE"
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
- NDIS_OFFLOAD_HANDLE
product:
- Windows
targetos: Windows
req.typenames: NDIS_OFFLOAD_HANDLE, *PNDIS_OFFLOAD_HANDLE
---

# _NDIS_OFFLOAD_HANDLE structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NDIS_OFFLOAD_HANDLE structure represents a driver's context for an offloaded state object.


## -struct-fields




### -field NdisReserved

Reserved for use by NDIS.


### -field MiniportOffloadContext

A pointer that references a host memory location into which the underlying driver writes a PVOID
     value when completing the initiate offload operation. This PVOID value references the underlying
     driver's offload context for the offloaded state object.


## -remarks



When propagating the offload of a TCP chimney state object, an intermediate driver supplies a pointer
    to an NDIS_OFFLOAD_HANDLE structure. This pointer, in effect, references the intermediate driver's
    context for the offloaded state object.

The NDIS_OFFLOAD_HANDLE structure contains a 
    <b>MiniportOffloadContext</b> pointer that references a memory location into which the underlying driver
    or offload target writes a PVOID value before completing the initiate offload operation. This PVOID value
    references the underlying driver's or offload target's context for the offloaded state object.

For more information about the use of the NDIS_OFFLOAD_HANDLE structure, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/referencing-offloaded-state-through-an-intermediate-driver">
    Referencing Offloaded State Through an Intermediate Driver</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_initiate_offload_handler">MiniportInitiateOffload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndisminitiateoffloadcomplete">NdisMInitiateOffloadComplete</a>
 

 

