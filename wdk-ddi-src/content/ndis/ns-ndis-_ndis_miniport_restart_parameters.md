---
UID: NS:ndis._NDIS_MINIPORT_RESTART_PARAMETERS
title: _NDIS_MINIPORT_RESTART_PARAMETERS (ndis.h)
description: The NDIS_MINIPORT_RESTART_PARAMETERS structure defines the restart parameters for a miniport adapter.
old-location: netvista\ndis_miniport_restart_parameters.htm
tech.root: netvista
ms.assetid: 4e005245-ed98-47fd-aaae-421940edf2dc
ms.date: 05/02/2018
ms.keywords: "*PNDIS_MINIPORT_RESTART_PARAMETERS, NDIS_MINIPORT_RESTART_PARAMETERS, NDIS_MINIPORT_RESTART_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_RESTART_PARAMETERS, PNDIS_MINIPORT_RESTART_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_RESTART_PARAMETERS, miniport_structures_ref_618076bd-9d88-4104-89fd-c2ccddf32b02.xml, ndis/NDIS_MINIPORT_RESTART_PARAMETERS, ndis/PNDIS_MINIPORT_RESTART_PARAMETERS, netvista.ndis_miniport_restart_parameters"
f1_keywords:
 - "ndis/NDIS_MINIPORT_RESTART_PARAMETERS"
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
- NDIS_MINIPORT_RESTART_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_RESTART_PARAMETERS, *PNDIS_MINIPORT_RESTART_PARAMETERS
---

# _NDIS_MINIPORT_RESTART_PARAMETERS structure


## -description


The NDIS_MINIPORT_RESTART_PARAMETERS structure defines the restart parameters for a miniport
  adapter.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_RESTART_PARAMETERS structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specified to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_MINIPORT_RESTART_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_MINIPORT_RESTART_PARAMETERS_REVISION_1.


### -field RestartAttributes

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_restart_attributes">
     NDIS_RESTART_ATTRIBUTES</a> structure.


### -field Flags

Reserved.


## -remarks



To define miniport adapter restart parameters, NDIS passes a pointer to an
    NDIS_MINIPORT_RESTART_PARAMETERS structure to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_restart">MiniportRestart</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_restart">MiniportRestart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_restart_attributes">NDIS_RESTART_ATTRIBUTES</a>
 

 

