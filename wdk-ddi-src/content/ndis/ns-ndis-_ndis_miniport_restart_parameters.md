---
UID: NS:ndis._NDIS_MINIPORT_RESTART_PARAMETERS
title: "_NDIS_MINIPORT_RESTART_PARAMETERS"
author: windows-driver-content
description: The NDIS_MINIPORT_RESTART_PARAMETERS structure defines the restart parameters for a miniport adapter.
old-location: netvista\ndis_miniport_restart_parameters.htm
old-project: netvista
ms.assetid: 4e005245-ed98-47fd-aaae-421940edf2dc
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_MINIPORT_RESTART_PARAMETERS, NDIS_MINIPORT_RESTART_PARAMETERS, NDIS_MINIPORT_RESTART_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_RESTART_PARAMETERS, PNDIS_MINIPORT_RESTART_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_RESTART_PARAMETERS, miniport_structures_ref_618076bd-9d88-4104-89fd-c2ccddf32b02.xml, ndis/NDIS_MINIPORT_RESTART_PARAMETERS, ndis/PNDIS_MINIPORT_RESTART_PARAMETERS, netvista.ndis_miniport_restart_parameters"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_MINIPORT_RESTART_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_RESTART_PARAMETERS, *PNDIS_MINIPORT_RESTART_PARAMETERS
---

# _NDIS_MINIPORT_RESTART_PARAMETERS structure


## -description


The NDIS_MINIPORT_RESTART_PARAMETERS structure defines the restart parameters for a miniport
  adapter.


## -syntax


````
typedef struct _NDIS_MINIPORT_RESTART_PARAMETERS {
  NDIS_OBJECT_HEADER       Header;
  PNDIS_RESTART_ATTRIBUTES RestartAttributes;
  ULONG                    Flags;
} NDIS_MINIPORT_RESTART_PARAMETERS, *PNDIS_MINIPORT_RESTART_PARAMETERS;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_RESTART_PARAMETERS structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specified to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_MINIPORT_RESTART_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_MINIPORT_RESTART_PARAMETERS_REVISION_1.


### -field RestartAttributes

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_restart_attributes.md">
     NDIS_RESTART_ATTRIBUTES</a> structure.


### -field Flags

Reserved.


## -remarks



To define miniport adapter restart parameters, NDIS passes a pointer to an
    NDIS_MINIPORT_RESTART_PARAMETERS structure to the 
    <a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a> function.




## -see-also

<a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndis\ns-ndis-_ndis_restart_attributes.md">NDIS_RESTART_ATTRIBUTES</a>



 

 


