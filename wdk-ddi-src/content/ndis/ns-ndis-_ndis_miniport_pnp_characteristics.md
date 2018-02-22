---
UID: NS:ndis._NDIS_MINIPORT_PNP_CHARACTERISTICS
title: "_NDIS_MINIPORT_PNP_CHARACTERISTICS"
author: windows-driver-content
description: The NDIS_MINIPORT_PNP_CHARACTERISTICS structure specifies entry points for functions that allow a miniport driver to process some Plug and Play (PnP) I/O request packets (IRPs).
old-location: netvista\ndis_miniport_pnp_characteristics.htm
old-project: netvista
ms.assetid: 97820a22-aa20-4d47-a4c2-0c0d50540823
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_MINIPORT_PNP_CHARACTERISTICS, NDIS_MINIPORT_PNP_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], ndis/PNDIS_MINIPORT_PNP_CHARACTERISTICS, PNDIS_MINIPORT_PNP_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_PNP_CHARACTERISTICS, NDIS_MINIPORT_PNP_CHARACTERISTICS, ndis_msix_ref_0f6182d0-b82c-4420-828e-e59d98fc82da.xml, ndis/NDIS_MINIPORT_PNP_CHARACTERISTICS, PNDIS_MINIPORT_PNP_CHARACTERISTICS, netvista.ndis_miniport_pnp_characteristics"
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
-	NDIS_MINIPORT_PNP_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_PNP_CHARACTERISTICS, *PNDIS_MINIPORT_PNP_CHARACTERISTICS
---

# _NDIS_MINIPORT_PNP_CHARACTERISTICS structure


## -description


The NDIS_MINIPORT_PNP_CHARACTERISTICS structure specifies entry points for functions that allow a
  miniport driver to process some Plug and Play (PnP) I/O request packets (IRPs).


## -syntax


````
typedef struct _NDIS_MINIPORT_PNP_CHARACTERISTICS {
  NDIS_OBJECT_HEADER                            Header;
  MINIPORT_ADD_DEVICE_HANDLER                   MiniportAddDeviceHandler;
  MINIPORT_REMOVE_DEVICE_HANDLER                MiniportRemoveDeviceHandler;
  MINIPORT_FILTER_RESOURCE_REQUIREMENTS_HANDLER MiniportFilterResourceRequirementsHandler;
  MINIPORT_START_DEVICE_HANDLER                 MiniportStartDeviceHandler;
  ULONG                                         Flags;
} NDIS_MINIPORT_PNP_CHARACTERISTICS, *PNDIS_MINIPORT_PNP_CHARACTERISTICS;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_PNP_CHARACTERISTICS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_PNP_CHARACTERISTICS, the 
     <b>Revision</b> member to NDIS_MINIPORT_PNP_CHARACTERISTICS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_MINIPORT_PNP_CHARACTERISTICS_REVISION_1.


### -field MiniportAddDeviceHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-miniport_add_device.md">MiniportAddDevice</a> function.


### -field MiniportRemoveDeviceHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-miniport_remove_device.md">
     MiniportRemoveDevice</a> function.


### -field MiniportFilterResourceRequirementsHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff559452(d=robot)">
     MiniportFilterResourceRequirements</a> function.


### -field MiniportStartDeviceHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-miniport_pnp_irp.md">MiniportStartDevice</a> function, if
     any. If this function is not required, set this member to <b>NULL</b>.


### -field Flags

Reserved.


## -remarks



Miniport drivers that support MSI-X and will change the interrupt affinity for each MSI-X message
    register functions that are defined in the NDIS_MINIPORT_PNP_CHARACTERISTICS structure. To register these
    functions, call the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> function
    from the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a> function and
    specify an NDIS_MINIPORT_PNP_CHARACTERISTICS structure at the 
    <i>OptionalHandlers</i> parameter of 
    <b>NdisSetOptionalHandlers</b>.




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a>



<a href="..\ndis\nc-ndis-miniport_add_device.md">MiniportAddDevice</a>



<a href="..\ndis\nc-ndis-miniport_remove_device.md">MiniportRemoveDevice</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559452(d=robot)">
   MiniportFilterResourceRequirements</a>



<a href="..\ndis\nc-ndis-miniport_remove_device.md">MiniportRemoveDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MINIPORT_PNP_CHARACTERISTICS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

