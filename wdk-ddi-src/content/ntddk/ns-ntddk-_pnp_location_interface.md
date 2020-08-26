---
UID: NS:ntddk._PNP_LOCATION_INTERFACE
title: _PNP_LOCATION_INTERFACE (ntddk.h)
description: The PNP_LOCATION_INTERFACE structure describes the GUID_PNP_LOCATION_INTERFACE interface.
old-location: kernel\pnp_location_interface.htm
tech.root: kernel
ms.assetid: 5189ffad-e5dc-4f5a-a7e3-481d36332c81
ms.date: 04/30/2018
keywords: ["PNP_LOCATION_INTERFACE structure"]
ms.keywords: "*PPNP_LOCATION_INTERFACE, PNP_LOCATION_INTERFACE, PNP_LOCATION_INTERFACE structure [Kernel-Mode Driver Architecture], PPNP_LOCATION_INTERFACE, PPNP_LOCATION_INTERFACE structure pointer [Kernel-Mode Driver Architecture], _PNP_LOCATION_INTERFACE, drvr_interface_06c9b5c0-359b-4b14-9ade-8f88f04ee534.xml, kernel.pnp_location_interface, ntddk/PNP_LOCATION_INTERFACE, ntddk/PPNP_LOCATION_INTERFACE"
f1_keywords:
 - "ntddk/PNP_LOCATION_INTERFACE"
 - "PNP_LOCATION_INTERFACE"
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Windows Server 2003 and later versions of the Windows operating system.
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
- Ntddk.h
api_name:
- PNP_LOCATION_INTERFACE
targetos: Windows
req.typenames: PNP_LOCATION_INTERFACE, *PPNP_LOCATION_INTERFACE
---

# _PNP_LOCATION_INTERFACE structure


## -description


The **PNP_LOCATION_INTERFACE** structure describes the [GUID_PNP_LOCATION_INTERFACE](https://docs.microsoft.com/windows-hardware/drivers/kernel/adding-a-pnp-device-to-a-running-system#using-guidpnplocationinterface) interface.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Version

The driver-defined version of the interface.


### -field Context

A pointer to interface-specific context information.


### -field InterfaceReference

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_reference">InterfaceReference</a> routine that increments the reference count for the interface. The PINTERFACE_REFERENCE function pointer type is defined in the Wdm.h header file.


### -field InterfaceDereference

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference">InterfaceDereference</a> routine that decrements the reference count for the interface. The PINTERFACE_DEREFERENCE function pointer type is defined in the Wdm.h header file.


### -field GetLocationString

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pget_location_string">PnpGetLocationString</a> routine for the interface. The routine supplies the device-specific part of the SPDRP_LOCATION_PATHS property for the device.


## -remarks



A driver obtains a pointer to the <b>PNP_LOCATION_INTERFACE</b> structure by sending an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a> IRP to its bus driver with <b>InterfaceType</b> set to GUID_PNP_LOCATION_INTERFACE.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference">InterfaceDereference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_reference">InterfaceReference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pget_location_string">PnpGetLocationString</a>
 

 

