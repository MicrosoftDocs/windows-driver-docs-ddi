---
UID: NS:ndis._NDIS_MINIPORT_PNP_CHARACTERISTICS
title: _NDIS_MINIPORT_PNP_CHARACTERISTICS (ndis.h)
description: The NDIS_MINIPORT_PNP_CHARACTERISTICS structure specifies entry points for functions that allow a miniport driver to process some Plug and Play (PnP) I/O request packets (IRPs).
old-location: netvista\ndis_miniport_pnp_characteristics.htm
tech.root: netvista
ms.assetid: 97820a22-aa20-4d47-a4c2-0c0d50540823
ms.date: 05/02/2018
keywords: ["NDIS_MINIPORT_PNP_CHARACTERISTICS structure"]
ms.keywords: "*PNDIS_MINIPORT_PNP_CHARACTERISTICS, NDIS_MINIPORT_PNP_CHARACTERISTICS, NDIS_MINIPORT_PNP_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_PNP_CHARACTERISTICS, PNDIS_MINIPORT_PNP_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_PNP_CHARACTERISTICS, ndis/NDIS_MINIPORT_PNP_CHARACTERISTICS, ndis/PNDIS_MINIPORT_PNP_CHARACTERISTICS, ndis_msix_ref_0f6182d0-b82c-4420-828e-e59d98fc82da.xml, netvista.ndis_miniport_pnp_characteristics"
f1_keywords:
 - "ndis/NDIS_MINIPORT_PNP_CHARACTERISTICS"
 - "NDIS_MINIPORT_PNP_CHARACTERISTICS"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
- ndis.h
api_name:
- NDIS_MINIPORT_PNP_CHARACTERISTICS
targetos: Windows
req.typenames: NDIS_MINIPORT_PNP_CHARACTERISTICS, *PNDIS_MINIPORT_PNP_CHARACTERISTICS
---

# _NDIS_MINIPORT_PNP_CHARACTERISTICS structure


## -description


The NDIS_MINIPORT_PNP_CHARACTERISTICS structure specifies entry points for functions that allow a
  miniport driver to process some Plug and Play (PnP) I/O request packets (IRPs).


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_PNP_CHARACTERISTICS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_PNP_CHARACTERISTICS, the 
     <b>Revision</b> member to NDIS_MINIPORT_PNP_CHARACTERISTICS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_MINIPORT_PNP_CHARACTERISTICS_REVISION_1.


### -field MiniportAddDeviceHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_add_device">MiniportAddDevice</a> function.


### -field MiniportRemoveDeviceHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_remove_device">
     MiniportRemoveDevice</a> function.


### -field MiniportFilterResourceRequirementsHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pnp_irp">
     MiniportFilterResourceRequirements</a> function.


### -field MiniportStartDeviceHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pnp_irp">MiniportStartDevice</a> function, if
     any. If this function is not required, set this member to <b>NULL</b>.


### -field Flags

Reserved.


## -remarks



Miniport drivers that support MSI-X and will change the interrupt affinity for each MSI-X message
    register functions that are defined in the NDIS_MINIPORT_PNP_CHARACTERISTICS structure. To register these
    functions, call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a> function
    from the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">MiniportSetOptions</a> function and
    specify an NDIS_MINIPORT_PNP_CHARACTERISTICS structure at the 
    <i>OptionalHandlers</i> parameter of 
    <b>NdisSetOptionalHandlers</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_add_device">MiniportAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pnp_irp">
   MiniportFilterResourceRequirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_remove_device">MiniportRemoveDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">MiniportSetOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pnp_irp">MiniportStartDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a>
 

 

