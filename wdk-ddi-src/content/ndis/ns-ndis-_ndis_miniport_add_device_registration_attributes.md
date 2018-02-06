---
UID: NS:ndis._NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES
title: "_NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES"
author: windows-driver-content
description: The NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure specifies a driver-defined context area for an added device.
old-location: netvista\ndis_miniport_add_device_registration_attributes.htm
old-project: netvista
ms.assetid: 7e8b5dbf-2d56-4278-8953-8e21ba1cee06
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, _NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, ndis/PNDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], *PNDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, netvista.ndis_miniport_add_device_registration_attributes, PNDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], ndis_msix_ref_e1fdccd6-c157-42e8-875e-bf5c77bfe5d9.xml, PNDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES
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
-	NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, *PNDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES
---

# _NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure


## -description


The NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure specifies a driver-defined context
  area for an added device.


## -syntax


````
typedef struct _NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES {
  NDIS_OBJECT_HEADER Header;
  NDIS_HANDLE        MiniportAddDeviceContext;
  ULONG              Flags;
} NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, *PNDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
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
    <a href="..\ndis\nc-ndis-miniport_add_device.md">MiniportAddDevice</a> function and pass
    this structure to the 
    <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">
    NdisMSetMiniportAttributes</a> function.

NDIS later passes the context handle in the 
    <b>MiniportAddDeviceContext</b> member of NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES to the 
    <i>MiniportAddDeviceContext</i> parameter of the 
    <a href="..\ndis\nc-ndis-miniport_remove_device.md">MiniportRemoveDevice</a>, 
    <a href="..\ndis\nc-ndis-miniport_pnp_irp.md">MiniportStartDevice</a>, and 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff559452(d=robot)">
    MiniportFilterResourceRequirements</a> functions. NDIS passes the same handle to the 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function in
    the 
    <b>MiniportAddDeviceContext</b> member of the 
    <a href="..\ndis\ns-ndis-_ndis_miniport_init_parameters.md">
    NDIS_MINIPORT_INIT_PARAMETERS</a> structure.



## -see-also

<a href="..\ndis\nc-ndis-miniport_pnp_irp.md">MiniportStartDevice</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559452(d=robot)">
   MiniportFilterResourceRequirements</a>

<a href="..\ndis\ns-ndis-_ndis_miniport_init_parameters.md">NDIS_MINIPORT_INIT_PARAMETERS</a>

<a href="..\ndis\nc-ndis-miniport_add_device.md">MiniportAddDevice</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>

<a href="..\ndis\nc-ndis-miniport_remove_device.md">MiniportRemoveDevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

