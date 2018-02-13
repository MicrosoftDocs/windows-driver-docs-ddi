---
UID: NS:ndis._NDIS_MINIPORT_RESTART_PARAMETERS
title: "_NDIS_MINIPORT_RESTART_PARAMETERS"
author: windows-driver-content
description: The NDIS_MINIPORT_RESTART_PARAMETERS structure defines the restart parameters for a miniport adapter.
old-location: netvista\ndis_miniport_restart_parameters.htm
old-project: netvista
ms.assetid: 4e005245-ed98-47fd-aaae-421940edf2dc
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/NDIS_MINIPORT_RESTART_PARAMETERS, netvista.ndis_miniport_restart_parameters, PNDIS_MINIPORT_RESTART_PARAMETERS, PNDIS_MINIPORT_RESTART_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], miniport_structures_ref_618076bd-9d88-4104-89fd-c2ccddf32b02.xml, NDIS_MINIPORT_RESTART_PARAMETERS, *PNDIS_MINIPORT_RESTART_PARAMETERS, _NDIS_MINIPORT_RESTART_PARAMETERS, NDIS_MINIPORT_RESTART_PARAMETERS structure [Network Drivers Starting with Windows Vista], ndis/PNDIS_MINIPORT_RESTART_PARAMETERS
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
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



<a href="..\ndis\ns-ndis-_ndis_restart_attributes.md">NDIS_RESTART_ATTRIBUTES</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MINIPORT_RESTART_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

