---
UID: NS:ndis._NDIS_MINIPORT_PNP_CHARACTERISTICS
title: "_NDIS_MINIPORT_PNP_CHARACTERISTICS"
author: windows-driver-content
description: The NDIS_MINIPORT_PNP_CHARACTERISTICS structure specifies entry points for functions that allow a miniport driver to process some Plug and Play (PnP) I/O request packets (IRPs).
old-location: netvista\ndis_miniport_pnp_characteristics.htm
tech.root: netvista
ms.assetid: 97820a22-aa20-4d47-a4c2-0c0d50540823
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: "*PNDIS_MINIPORT_PNP_CHARACTERISTICS, NDIS_MINIPORT_PNP_CHARACTERISTICS, NDIS_MINIPORT_PNP_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_PNP_CHARACTERISTICS, PNDIS_MINIPORT_PNP_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_PNP_CHARACTERISTICS, ndis/NDIS_MINIPORT_PNP_CHARACTERISTICS, ndis/PNDIS_MINIPORT_PNP_CHARACTERISTICS, ndis_msix_ref_0f6182d0-b82c-4420-828e-e59d98fc82da.xml, netvista.ndis_miniport_pnp_characteristics"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_MINIPORT_PNP_CHARACTERISTICS
product:
- Windows
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
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_PNP_CHARACTERISTICS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_PNP_CHARACTERISTICS, the 
     <b>Revision</b> member to NDIS_MINIPORT_PNP_CHARACTERISTICS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_MINIPORT_PNP_CHARACTERISTICS_REVISION_1.


### -field MiniportAddDeviceHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/50e04b5a-e430-484c-aabb-cc7b9ecb53b0">MiniportAddDevice</a> function.


### -field MiniportRemoveDeviceHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/24dd887b-575f-4790-bb53-7c3fb825bd61">
     MiniportRemoveDevice</a> function.


### -field MiniportFilterResourceRequirementsHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff559452(d=robot)">
     MiniportFilterResourceRequirements</a> function.


### -field MiniportStartDeviceHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/ccccb2c5-16ba-4463-bb35-1dc3dcc61a2f">MiniportStartDevice</a> function, if
     any. If this function is not required, set this member to <b>NULL</b>.


### -field Flags

Reserved.


## -remarks



Miniport drivers that support MSI-X and will change the interrupt affinity for each MSI-X message
    register functions that are defined in the NDIS_MINIPORT_PNP_CHARACTERISTICS structure. To register these
    functions, call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a> function
    from the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570269">MiniportSetOptions</a> function and
    specify an NDIS_MINIPORT_PNP_CHARACTERISTICS structure at the 
    <i>OptionalHandlers</i> parameter of 
    <b>NdisSetOptionalHandlers</b>.




## -see-also




<a href="https://msdn.microsoft.com/50e04b5a-e430-484c-aabb-cc7b9ecb53b0">MiniportAddDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559452(d=robot)">
   MiniportFilterResourceRequirements</a>



<a href="https://msdn.microsoft.com/24dd887b-575f-4790-bb53-7c3fb825bd61">MiniportRemoveDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570269">MiniportSetOptions</a>



<a href="https://msdn.microsoft.com/ccccb2c5-16ba-4463-bb35-1dc3dcc61a2f">MiniportStartDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>
 

 

