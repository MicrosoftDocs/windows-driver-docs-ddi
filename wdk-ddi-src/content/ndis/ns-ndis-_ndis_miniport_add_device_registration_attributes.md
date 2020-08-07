---
UID: NS:ndis._NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES
title: _NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES (ndis.h)
description: The NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure specifies a driver-defined context area for an added device.
old-location: netvista\ndis_miniport_add_device_registration_attributes.htm
tech.root: netvista
ms.assetid: 7e8b5dbf-2d56-4278-8953-8e21ba1cee06
ms.date: 05/02/2018
keywords: ["NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure"]
ms.keywords: "*PNDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, PNDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, ndis/NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, ndis/PNDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, ndis_msix_ref_e1fdccd6-c157-42e8-875e-bf5c77bfe5d9.xml, netvista.ndis_miniport_add_device_registration_attributes"
f1_keywords:
 - "ndis/NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES"
 - "NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES"
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
- NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES
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
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_add_device">MiniportAddDevice</a> function and pass
    this structure to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">
    NdisMSetMiniportAttributes</a> function.

NDIS later passes the context handle in the 
    <b>MiniportAddDeviceContext</b> member of NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES to the 
    <i>MiniportAddDeviceContext</i> parameter of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_remove_device">MiniportRemoveDevice</a>, 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pnp_irp">MiniportStartDevice</a>, and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pnp_irp">
    MiniportFilterResourceRequirements</a> functions. NDIS passes the same handle to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function in
    the 
    <b>MiniportAddDeviceContext</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_init_parameters">
    NDIS_MINIPORT_INIT_PARAMETERS</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_add_device">MiniportAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pnp_irp">
   MiniportFilterResourceRequirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_remove_device">MiniportRemoveDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pnp_irp">MiniportStartDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_init_parameters">NDIS_MINIPORT_INIT_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>
 

 

