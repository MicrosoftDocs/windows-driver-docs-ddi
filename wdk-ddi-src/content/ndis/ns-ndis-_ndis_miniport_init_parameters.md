---
UID: NS:ndis._NDIS_MINIPORT_INIT_PARAMETERS
title: _NDIS_MINIPORT_INIT_PARAMETERS (ndis.h)
description: The NDIS_MINIPORT_INIT_PARAMETERS structure defines the initialization parameters for a miniport adapter.
old-location: netvista\ndis_miniport_init_parameters.htm
tech.root: netvista
ms.assetid: 945d921b-3024-4c4f-a50d-e996c6183db7
ms.date: 05/02/2018
keywords: ["NDIS_MINIPORT_INIT_PARAMETERS structure"]
ms.keywords: "*PNDIS_MINIPORT_INIT_PARAMETERS, NDIS_MINIPORT_INIT_PARAMETERS, NDIS_MINIPORT_INIT_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_INIT_PARAMETERS, PNDIS_MINIPORT_INIT_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_INIT_PARAMETERS, miniport_structures_ref_064614b0-eb2a-4fdd-8b0a-d14540e6faa5.xml, ndis/NDIS_MINIPORT_INIT_PARAMETERS, ndis/PNDIS_MINIPORT_INIT_PARAMETERS, netvista.ndis_miniport_init_parameters"
f1_keywords:
 - "ndis/NDIS_MINIPORT_INIT_PARAMETERS"
 - "NDIS_MINIPORT_INIT_PARAMETERS"
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
- NDIS_MINIPORT_INIT_PARAMETERS
targetos: Windows
req.typenames: NDIS_MINIPORT_INIT_PARAMETERS, *PNDIS_MINIPORT_INIT_PARAMETERS
---

# _NDIS_MINIPORT_INIT_PARAMETERS structure


## -description


The <b>NDIS_MINIPORT_INIT_PARAMETERS</b> structure defines the initialization parameters for a miniport
  adapter.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_INIT_PARAMETERS structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specified to NDIS_OBJECT_TYPE_MINIPORT_INIT_PARAMETERS, the 
     <b>Revision</b> member to NDIS_MINIPORT_INIT_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_MINIPORT_INIT_PARAMETER_REVISION_1.


### -field Flags

Reserved for NDIS.


### -field AllocatedResources

A pointer to an NDIS_RESOURCE_LIST-type structure that lists the hardware resources that the Plug
     and Play Manager assigned to the miniport adapter. The NDIS_RESOURCE_LIST is type definition that is
     equivalent to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_list">CM_PARTIAL_RESOURCE_LIST</a> on Windows
     2000 and later platforms.


### -field IMDeviceInstanceContext

A pointer to the context area for a virtual device that an intermediate driver supports. The
     driver passed this pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisiminitializedeviceinstanceex">
     NdisIMInitializeDeviceInstanceEx</a> function at the 
     <i>DeviceContext</i> parameter. If the miniport driver is not an intermediate driver, 
     <b>IMDeviceInstanceContext</b> is <b>NULL</b>.


### -field MiniportAddDeviceContext

A handle for a driver-allocated context area, or <b>NULL</b>. The miniport driver specifies this handle,
     if any, in the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_add_device">MiniportAddDevice</a> function.


### -field IfIndex

The network interface index that is associated with the miniport adapter.


### -field NetLuid

The 
     <a href="https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-net_luid_lh">NET_LUID</a> value that is associated with the
     miniport adapter.


### -field DefaultPortAuthStates

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_port_authentication_parameters">
     NDIS_PORT_AUTHENTICATION_PARAMETERS</a> structure that defines the default port authentication
     parameters for the miniport adapter. For more information about port authentication parameters, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-port-authentication-parameters">
     OID_GEN_PORT_AUTHENTICATION_PARAMETERS</a>.


### -field PciDeviceCustomProperties

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_pci_device_custom_properties">
     NDIS_PCI_DEVICE_CUSTOM_PROPERTIES</a> structure that defines the PCI custom properties for the
     miniport adapter.


## -remarks



NDIS passes a pointer to an initialized <b>NDIS_MINIPORT_INIT_PARAMETERS</b> structure in the 
    <i>MiniportInitParameters</i> parameter of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_list">CM_PARTIAL_RESOURCE_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_add_device">MiniportAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_pci_device_custom_properties">
   NDIS_PCI_DEVICE_CUSTOM_PROPERTIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_port_authentication_parameters">
   NDIS_PORT_AUTHENTICATION_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-net_luid_lh">NET_LUID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisiminitializedeviceinstanceex">
   NdisIMInitializeDeviceInstanceEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-port-authentication-parameters">
   OID_GEN_PORT_AUTHENTICATION_PARAMETERS</a>
 

 

