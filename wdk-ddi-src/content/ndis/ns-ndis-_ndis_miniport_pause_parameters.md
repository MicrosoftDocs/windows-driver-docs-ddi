---
UID: NS:ndis._NDIS_MINIPORT_PAUSE_PARAMETERS
title: "_NDIS_MINIPORT_PAUSE_PARAMETERS" (ndis.h)
description: The NDIS_MINIPORT_PAUSE_PARAMETERS structure defines pause parameters for miniport adapters.
old-location: netvista\ndis_miniport_pause_parameters.htm
tech.root: netvista
ms.assetid: 2d442ff7-37dd-4288-aadf-1ae04f98364c
ms.date: 05/02/2018
ms.keywords: "*PNDIS_MINIPORT_PAUSE_PARAMETERS, NDIS_MINIPORT_PAUSE_PARAMETERS, NDIS_MINIPORT_PAUSE_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_PAUSE_PARAMETERS, PNDIS_MINIPORT_PAUSE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_PAUSE_PARAMETERS, miniport_structures_ref_cd7d1bc3-5c65-45c5-8e45-f23619dafff8.xml, ndis/NDIS_MINIPORT_PAUSE_PARAMETERS, ndis/PNDIS_MINIPORT_PAUSE_PARAMETERS, netvista.ndis_miniport_pause_parameters"
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
-	NDIS_MINIPORT_PAUSE_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_PAUSE_PARAMETERS, *PNDIS_MINIPORT_PAUSE_PARAMETERS
---

# _NDIS_MINIPORT_PAUSE_PARAMETERS structure


## -description


The NDIS_MINIPORT_PAUSE_PARAMETERS structure defines pause parameters for miniport adapters.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_PAUSE_PARAMETERS structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_MINIPORT_PAUSE_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_MINIPORT_PAUSE_PARAMETERS_REVISION_1.


### -field Flags

Reserved.


### -field PauseReason

<div class="alert"><b>Note</b>  This member is deprecated for NDIS 6.40 and later drivers.</div>
<div> </div>
The value will always be NDIS_PAUSE_NDIS_INTERNAL.


## -remarks



To define miniport adapter pause parameters, NDIS passes a pointer to an
    NDIS_MINIPORT_PAUSE_PARAMETERS structure to the 
    <a href="https://msdn.microsoft.com/047241a5-6f52-4a82-a334-8508f0de5e1a">MiniportPause</a> function.




## -see-also




<a href="https://msdn.microsoft.com/047241a5-6f52-4a82-a334-8508f0de5e1a">MiniportPause</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>
 

 

