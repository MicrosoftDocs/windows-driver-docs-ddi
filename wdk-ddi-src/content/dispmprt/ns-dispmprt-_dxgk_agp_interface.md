---
UID: NS:dispmprt._DXGK_AGP_INTERFACE
title: _DXGK_AGP_INTERFACE (dispmprt.h)
description: The DXGK_AGP_INTERFACE structure contains pointers to functions in the AGP interface, which is implemented by the display port driver.
old-location: display\dxgk_agp_interface.htm
tech.root: display
ms.assetid: ebaa2aba-426f-4f5f-b2bf-a8433cdc9205
ms.date: 05/10/2018
keywords: ["_DXGK_AGP_INTERFACE structure"]
ms.keywords: "*PDXGK_AGP_INTERFACE, DXGK_AGP_INTERFACE, DXGK_AGP_INTERFACE structure [Display Devices], DmStructs_787b846e-2c2b-4fba-aa99-979a195c4305.xml, PDXGK_AGP_INTERFACE, PDXGK_AGP_INTERFACE structure pointer [Display Devices], _DXGK_AGP_INTERFACE, display.dxgk_agp_interface, dispmprt/DXGK_AGP_INTERFACE, dispmprt/PDXGK_AGP_INTERFACE"
f1_keywords:
 - "dispmprt/DXGK_AGP_INTERFACE"
 - "DXGK_AGP_INTERFACE"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
- dispmprt.h
api_name:
- DXGK_AGP_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: DXGK_AGP_INTERFACE, *PDXGK_AGP_INTERFACE
---

# _DXGK_AGP_INTERFACE structure


## -description


The DXGK_AGP_INTERFACE structure contains pointers to functions in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">AGP interface</a>, which is implemented by the display port driver.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Version

The version number of the AGP interface. Version number constants are defined in <i>Dispmprt.h</i> (for example, DXGK_AGP_INTERFACE_VERSION_1).


### -field Context

A pointer to a context that is provided by the display port driver.


### -field InterfaceReference

A pointer to an interface reference function that is implemented by the display port driver.


### -field InterfaceDereference

A pointer to an interface dereference function that is implemented by the display port driver.


### -field AgpAllocatePool

A pointer to the display port driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_agp_allocate_pool">AgpAllocatePool</a> function.


### -field AgpFreePool

A pointer to the display port driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_agp_free_pool">AgpFreePool</a> function.


### -field AgpSetCommand

A pointer to the display port driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_agp_set_command">AgpSetCommand</a> function.


## -remarks



The display miniport driver supplies the <b>Size</b> and <b>Version</b> members of this structure, and then calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_query_services">DxgkCbQueryServices</a>, which fills in the remaining members of this structure.



