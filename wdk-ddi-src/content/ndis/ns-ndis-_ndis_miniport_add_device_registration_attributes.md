---
UID: NS:ndis._NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES
title: "_NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES" (ndis.h)
description: The NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure specifies a driver-defined context area for an added device.
old-location: netvista\ndis_miniport_add_device_registration_attributes.htm
tech.root: netvista
ms.assetid: 7e8b5dbf-2d56-4278-8953-8e21ba1cee06
ms.date: 05/02/2018
ms.keywords: "*PNDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, PNDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, ndis/NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, ndis/PNDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, ndis_msix_ref_e1fdccd6-c157-42e8-875e-bf5c77bfe5d9.xml, netvista.ndis_miniport_add_device_registration_attributes"
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
-	NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES
product:
- Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, *PNDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES
---

# _NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure


## -description


The NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure specifies a driver-defined context
  area for an added device.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, the 
     <b>Revision</b> member to NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES_REVISION_1.


### -field MiniportAddDeviceContext

A handle for a driver-allocated context area.


### -field Flags

Reserved.


## -remarks



Miniport drivers initialize an NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure in the 
    <a href="https://msdn.microsoft.com/50e04b5a-e430-484c-aabb-cc7b9ecb53b0">MiniportAddDevice</a> function and pass
    this structure to the 
    <a href="https://msdn.microsoft.com/861626af-23ea-40dc-a91a-7da42d4b0a1c">
    NdisMSetMiniportAttributes</a> function.

NDIS later passes the context handle in the 
    <b>MiniportAddDeviceContext</b> member of NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES to the 
    <i>MiniportAddDeviceContext</i> parameter of the 
    <a href="https://msdn.microsoft.com/24dd887b-575f-4790-bb53-7c3fb825bd61">MiniportRemoveDevice</a>, 
    <a href="https://msdn.microsoft.com/ccccb2c5-16ba-4463-bb35-1dc3dcc61a2f">MiniportStartDevice</a>, and 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff559452(d=robot)">
    MiniportFilterResourceRequirements</a> functions. NDIS passes the same handle to the 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function in
    the 
    <b>MiniportAddDeviceContext</b> member of the 
    <a href="https://msdn.microsoft.com/945d921b-3024-4c4f-a50d-e996c6183db7">
    NDIS_MINIPORT_INIT_PARAMETERS</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/50e04b5a-e430-484c-aabb-cc7b9ecb53b0">MiniportAddDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559452(d=robot)">
   MiniportFilterResourceRequirements</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/24dd887b-575f-4790-bb53-7c3fb825bd61">MiniportRemoveDevice</a>



<a href="https://msdn.microsoft.com/ccccb2c5-16ba-4463-bb35-1dc3dcc61a2f">MiniportStartDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565972">NDIS_MINIPORT_INIT_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a>
 

 

