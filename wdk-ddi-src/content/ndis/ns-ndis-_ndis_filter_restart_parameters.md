---
UID: NS:ndis._NDIS_FILTER_RESTART_PARAMETERS
title: _NDIS_FILTER_RESTART_PARAMETERS (ndis.h)
description: The NDIS_FILTER_RESTART_PARAMETERS structure defines the restart parameters for the filter module.
old-location: netvista\ndis_filter_restart_parameters.htm
tech.root: netvista
ms.assetid: f61e8c1b-5cc5-4d61-a4e2-39ca402cd710
ms.date: 05/02/2018
ms.keywords: "*PNDIS_FILTER_RESTART_PARAMETERS, NDIS_FILTER_RESTART_PARAMETERS, NDIS_FILTER_RESTART_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_FILTER_RESTART_PARAMETERS, PNDIS_FILTER_RESTART_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_FILTER_RESTART_PARAMETERS, filter_structures_ref_35344063-f39b-4a73-8069-4a47a61d9f2a.xml, ndis/NDIS_FILTER_RESTART_PARAMETERS, ndis/PNDIS_FILTER_RESTART_PARAMETERS, netvista.ndis_filter_restart_parameters"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_FILTER_RESTART_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_FILTER_RESTART_PARAMETERS, *PNDIS_FILTER_RESTART_PARAMETERS
---

# _NDIS_FILTER_RESTART_PARAMETERS structure


## -description


The NDIS_FILTER_RESTART_PARAMETERS structure defines the restart parameters for the filter
  module.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure
     for the NDIS_FILTER_RESTART_PARAMETERS structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_FILTER_RESTART_PARAMETERS, the 
     <b>Revision</b> member to NDIS_FILTER_RESTART_PARAMETERS_REVISION_1, and the Size member to
     NDIS_SIZEOF__FILTER_RESTART_PARAMETERS_REVISION_1.


### -field MiniportMediaType

The 
     NdisMedium
     <i>Xxx</i> type that the base underlying miniport adapter supports. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff565910">NDIS_MEDIUM</a>.


### -field MiniportPhysicalMediaType

The physical medium type for the base underlying miniport adapter. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569621">OID_GEN_PHYSICAL_MEDIUM</a>.


### -field RestartAttributes

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_restart_attributes">NDIS_RESTART_ATTRIBUTES</a> structure.
     


### -field LowerIfIndex

The NDIS network interface index of the interface just below the current filter module. That is,
     if there are filter modules or NDIS 5.<i>x</i> filter intermediate drivers that are installed over a physical miniport adapter or the
     highest-level MUX intermediate driver, this member contains the interface index of the filter module
     interface or filter intermediate driver interface that is just below the current filter module. If there
     are no filter module or filter intermediate driver interfaces installed over the physical miniport
     adapter or the highest-level MUX intermediate driver, this member contains the interface index of the
     underlying physical miniport adapter or the highest-level MUX intermediate driver virtual
     miniport.


### -field LowerIfNetLuid

The NDIS network interface 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a> value of the interface just below the
     current filter module. That is, if there are filter modules or NDIS 5.<i>x</i> filter intermediate drivers that are installed over a physical miniport adapter or the
     highest-level MUX intermediate driver, this member contains the network interface NET_LUID of the filter
     module interface or filter intermediate driver interface that is just below the current filter module.
     If there are no filter module or filter intermediate driver interfaces installed over the physical
     miniport adapter or the highest-level MUX intermediate driver, this member contains the network
     interface NET_LUID of the underlying physical miniport adapter or the highest-level MUX intermediate
     driver virtual miniport.


### -field Flags

Reserved for future use.


## -remarks



To define filter module restart parameters, NDIS passes a pointer to an NDIS_FILTER_RESART_PARAMETERS
    structure to the 
    <a href="https://msdn.microsoft.com/4a917824-eef1-4945-b45e-1c940bc8a50d">FilterRestart</a> function.

Filter drivers can modify the restart attributes that are specified by underlying drivers. For more
    information about how to modify restart attributes, see 
    <a href="https://msdn.microsoft.com/4a917824-eef1-4945-b45e-1c940bc8a50d">FilterRestart</a>.




## -see-also




<a href="https://msdn.microsoft.com/4a917824-eef1-4945-b45e-1c940bc8a50d">FilterRestart</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565910">NDIS_MEDIUM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567255">NDIS_RESTART_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569621">OID_GEN_PHYSICAL_MEDIUM</a>
 

 

