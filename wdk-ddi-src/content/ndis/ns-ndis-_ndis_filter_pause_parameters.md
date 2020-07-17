---
UID: NS:ndis._NDIS_FILTER_PAUSE_PARAMETERS
title: _NDIS_FILTER_PAUSE_PARAMETERS (ndis.h)
description: The NDIS_FILTER_PAUSE_PARAMETERS structure defines the pause parameters for the filter module.
old-location: netvista\ndis_filter_pause_parameters.htm
tech.root: netvista
ms.assetid: 070c6d5d-9942-4bff-8894-9aa69d5e7983
ms.date: 05/02/2018
keywords: ["_NDIS_FILTER_PAUSE_PARAMETERS structure"]
ms.keywords: "*PNDIS_FILTER_PAUSE_PARAMETERS, NDIS_FILTER_PAUSE_PARAMETERS, NDIS_FILTER_PAUSE_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_FILTER_PAUSE_PARAMETERS, PNDIS_FILTER_PAUSE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_FILTER_PAUSE_PARAMETERS, filter_structures_ref_78bd5df6-c235-4af1-9b2f-1ddce38a0017.xml, ndis/NDIS_FILTER_PAUSE_PARAMETERS, ndis/PNDIS_FILTER_PAUSE_PARAMETERS, netvista.ndis_filter_pause_parameters"
f1_keywords:
 - "ndis/NDIS_FILTER_PAUSE_PARAMETERS"
 - "NDIS_FILTER_PAUSE_PARAMETERS"
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
- NDIS_FILTER_PAUSE_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_FILTER_PAUSE_PARAMETERS, *PNDIS_FILTER_PAUSE_PARAMETERS
---

# _NDIS_FILTER_PAUSE_PARAMETERS structure


## -description


The NDIS_FILTER_PAUSE_PARAMETERS structure defines the pause parameters for the filter module.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_FILTER_PAUSE_PARAMETERS structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_FILTER_PAUSE_PARAMETERS, the 
     <b>Revision</b> member to NDIS_FILTER_PAUSE_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_FILTER_PAUSE_PARAMETERS_REVISION_1.


### -field Flags

Reserved.


### -field PauseReason

<div class="alert"><b>Note</b>  This member is deprecated for NDIS 6.40 and later drivers.</div>
<div> </div>
The value will always be NDIS_PAUSE_NDIS_INTERNAL.


## -remarks



To define filter module pause parameters, NDIS passes a pointer to an NDIS_FILTER_PAUSE_PARAMETERS
    structure to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_pause">FilterPause</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_pause">FilterPause</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>
 

 

