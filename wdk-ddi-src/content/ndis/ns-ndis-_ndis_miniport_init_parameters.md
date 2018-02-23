---
UID: NS:ndis._NDIS_MINIPORT_INIT_PARAMETERS
title: "_NDIS_MINIPORT_INIT_PARAMETERS"
author: windows-driver-content
description: The NDIS_MINIPORT_INIT_PARAMETERS structure defines the initialization parameters for a miniport adapter.
old-location: netvista\ndis_miniport_init_parameters.htm
old-project: netvista
ms.assetid: 945d921b-3024-4c4f-a50d-e996c6183db7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NDIS_MINIPORT_INIT_PARAMETERS, ndis/NDIS_MINIPORT_INIT_PARAMETERS, *PNDIS_MINIPORT_INIT_PARAMETERS, ndis/PNDIS_MINIPORT_INIT_PARAMETERS, netvista.ndis_miniport_init_parameters, PNDIS_MINIPORT_INIT_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_INIT_PARAMETERS, NDIS_MINIPORT_INIT_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_INIT_PARAMETERS, miniport_structures_ref_064614b0-eb2a-4fdd-8b0a-d14540e6faa5.xml
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
-	NDIS_MINIPORT_INIT_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_INIT_PARAMETERS, *PNDIS_MINIPORT_INIT_PARAMETERS
---

# _NDIS_MINIPORT_INIT_PARAMETERS structure


## -description


The <b>NDIS_MINIPORT_INIT_PARAMETERS</b> structure defines the initialization parameters for a miniport
  adapter.


## -syntax


````
typedef struct _NDIS_MINIPORT_INIT_PARAMETERS {
  NDIS_OBJECT_HEADER                   Header;
  ULONG                                Flags;
  PNDIS_RESOURCE_LIST                  AllocatedResources;
  NDIS_HANDLE                          IMDeviceInstanceContext;
  NDIS_HANDLE                          MiniportAddDeviceContext;
  NET_IFINDEX                          IfIndex;
  NET_LUID                             NetLuid;
  PNDIS_PORT_AUTHENTICATION_PARAMETERS DefaultPortAuthStates;
  PNDIS_PCI_DEVICE_CUSTOM_PROPERTIES   PciDeviceCustomProperties;
} NDIS_MINIPORT_INIT_PARAMETERS, *PNDIS_MINIPORT_INIT_PARAMETERS;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
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
     <a href="..\wudfwdm\ns-wudfwdm-_cm_partial_resource_list.md">CM_PARTIAL_RESOURCE_LIST</a> on Windows
     2000 and later platforms.


### -field IMDeviceInstanceContext

A pointer to the context area for a virtual device that an intermediate driver supports. The
     driver passed this pointer to the 
     <a href="..\ndis\nf-ndis-ndisiminitializedeviceinstanceex.md">
     NdisIMInitializeDeviceInstanceEx</a> function at the 
     <i>DeviceContext</i> parameter. If the miniport driver is not an intermediate driver, 
     <b>IMDeviceInstanceContext</b> is <b>NULL</b>.


### -field MiniportAddDeviceContext

A handle for a driver-allocated context area, or <b>NULL</b>. The miniport driver specifies this handle,
     if any, in the 
     <a href="..\ndis\nc-ndis-miniport_add_device.md">MiniportAddDevice</a> function.


### -field IfIndex

The network interface index that is associated with the miniport adapter.


### -field NetLuid

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a> value that is associated with the
     miniport adapter.


### -field DefaultPortAuthStates

A pointer to an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_port_authentication_parameters.md">
     NDIS_PORT_AUTHENTICATION_PARAMETERS</a> structure that defines the default port authentication
     parameters for the miniport adapter. For more information about port authentication parameters, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-port-authentication-parameters">
     OID_GEN_PORT_AUTHENTICATION_PARAMETERS</a>.


### -field PciDeviceCustomProperties

A pointer to an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_pci_device_custom_properties.md">
     NDIS_PCI_DEVICE_CUSTOM_PROPERTIES</a> structure that defines the PCI custom properties for the
     miniport adapter.


## -remarks



NDIS passes a pointer to an initialized <b>NDIS_MINIPORT_INIT_PARAMETERS</b> structure in the 
    <i>MiniportInitParameters</i> parameter of the 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_pci_device_custom_properties.md">
   NDIS_PCI_DEVICE_CUSTOM_PROPERTIES</a>



<a href="..\ndis\nc-ndis-miniport_add_device.md">MiniportAddDevice</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-port-authentication-parameters">
   OID_GEN_PORT_AUTHENTICATION_PARAMETERS</a>



<a href="..\ndis\nf-ndis-ndisiminitializedeviceinstanceex.md">
   NdisIMInitializeDeviceInstanceEx</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_port_authentication_parameters.md">
   NDIS_PORT_AUTHENTICATION_PARAMETERS</a>



<a href="..\wudfwdm\ns-wudfwdm-_cm_partial_resource_list.md">CM_PARTIAL_RESOURCE_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MINIPORT_INIT_PARAMETERS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

