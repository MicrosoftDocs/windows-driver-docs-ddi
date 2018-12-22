---
UID: NS:ndis._NDIS_MINIPORT_INIT_PARAMETERS
title: "_NDIS_MINIPORT_INIT_PARAMETERS"
description: The NDIS_MINIPORT_INIT_PARAMETERS structure defines the initialization parameters for a miniport adapter.
old-location: netvista\ndis_miniport_init_parameters.htm
tech.root: netvista
ms.assetid: 945d921b-3024-4c4f-a50d-e996c6183db7
ms.date: 05/02/2018
ms.keywords: "*PNDIS_MINIPORT_INIT_PARAMETERS, NDIS_MINIPORT_INIT_PARAMETERS, NDIS_MINIPORT_INIT_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_INIT_PARAMETERS, PNDIS_MINIPORT_INIT_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_INIT_PARAMETERS, miniport_structures_ref_064614b0-eb2a-4fdd-8b0a-d14540e6faa5.xml, ndis/NDIS_MINIPORT_INIT_PARAMETERS, ndis/PNDIS_MINIPORT_INIT_PARAMETERS, netvista.ndis_miniport_init_parameters"
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
-	NDIS_MINIPORT_INIT_PARAMETERS
product:
- Windows
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
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
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
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff541981">CM_PARTIAL_RESOURCE_LIST</a> on Windows
     2000 and later platforms.


### -field IMDeviceInstanceContext

A pointer to the context area for a virtual device that an intermediate driver supports. The
     driver passed this pointer to the 
     <a href="https://msdn.microsoft.com/f65c2974-4bf4-4948-ac07-527e69c96303">
     NdisIMInitializeDeviceInstanceEx</a> function at the 
     <i>DeviceContext</i> parameter. If the miniport driver is not an intermediate driver, 
     <b>IMDeviceInstanceContext</b> is <b>NULL</b>.


### -field MiniportAddDeviceContext

A handle for a driver-allocated context area, or <b>NULL</b>. The miniport driver specifies this handle,
     if any, in the 
     <a href="https://msdn.microsoft.com/50e04b5a-e430-484c-aabb-cc7b9ecb53b0">MiniportAddDevice</a> function.


### -field IfIndex

The network interface index that is associated with the miniport adapter.


### -field NetLuid

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a> value that is associated with the
     miniport adapter.


### -field DefaultPortAuthStates

A pointer to an 
     <a href="https://msdn.microsoft.com/7c411d9e-1064-4278-9870-0546891d4743">
     NDIS_PORT_AUTHENTICATION_PARAMETERS</a> structure that defines the default port authentication
     parameters for the miniport adapter. For more information about port authentication parameters, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-port-authentication-parameters">
     OID_GEN_PORT_AUTHENTICATION_PARAMETERS</a>.


### -field PciDeviceCustomProperties

A pointer to an 
     <a href="https://msdn.microsoft.com/fd61184f-0502-492d-9014-6afbfd70c189">
     NDIS_PCI_DEVICE_CUSTOM_PROPERTIES</a> structure that defines the PCI custom properties for the
     miniport adapter.


## -remarks



NDIS passes a pointer to an initialized <b>NDIS_MINIPORT_INIT_PARAMETERS</b> structure in the 
    <i>MiniportInitParameters</i> parameter of the 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541981">CM_PARTIAL_RESOURCE_LIST</a>



<a href="https://msdn.microsoft.com/50e04b5a-e430-484c-aabb-cc7b9ecb53b0">MiniportAddDevice</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/fd61184f-0502-492d-9014-6afbfd70c189">
   NDIS_PCI_DEVICE_CUSTOM_PROPERTIES</a>



<a href="https://msdn.microsoft.com/7c411d9e-1064-4278-9870-0546891d4743">
   NDIS_PORT_AUTHENTICATION_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a>



<a href="https://msdn.microsoft.com/f65c2974-4bf4-4948-ac07-527e69c96303">
   NdisIMInitializeDeviceInstanceEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-port-authentication-parameters">
   OID_GEN_PORT_AUTHENTICATION_PARAMETERS</a>
 

 

