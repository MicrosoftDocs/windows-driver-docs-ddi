---
UID: NS:dispmprt._DXGK_AGP_INTERFACE
title: DXGK_AGP_INTERFACE (dispmprt.h)
description: The DXGK_AGP_INTERFACE structure contains pointers to functions in the AGP interface, which is implemented by the display port driver.
old-location: display\dxgk_agp_interface.htm
tech.root: display
ms.date: 11/19/2021
keywords: ["DXGK_AGP_INTERFACE structure"]
ms.keywords: "*PDXGK_AGP_INTERFACE, DXGK_AGP_INTERFACE, DXGK_AGP_INTERFACE structure [Display Devices], DmStructs_787b846e-2c2b-4fba-aa99-979a195c4305.xml, PDXGK_AGP_INTERFACE, PDXGK_AGP_INTERFACE structure pointer [Display Devices], _DXGK_AGP_INTERFACE, display.dxgk_agp_interface, dispmprt/DXGK_AGP_INTERFACE, dispmprt/PDXGK_AGP_INTERFACE"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
targetos: Windows
req.typenames: DXGK_AGP_INTERFACE, *PDXGK_AGP_INTERFACE
f1_keywords:
 - _DXGK_AGP_INTERFACE
 - dispmprt/_DXGK_AGP_INTERFACE
 - PDXGK_AGP_INTERFACE
 - dispmprt/PDXGK_AGP_INTERFACE
 - DXGK_AGP_INTERFACE
 - dispmprt/DXGK_AGP_INTERFACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_AGP_INTERFACE
 - PDXGK_AGP_INTERFACE
 - DXGK_AGP_INTERFACE
---

# DXGK_AGP_INTERFACE structure

## -description

The **DXGK_AGP_INTERFACE** structure contains pointers to functions in the Accelerated Graphics Port (AGP) interface, which is implemented by the display port driver.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Version

The version number of the AGP interface. Version number constants are defined in *Dispmprt.h* (for example, DXGK_AGP_INTERFACE_VERSION_1).

### -field Context

A pointer to a context that is provided by the display port driver.

### -field InterfaceReference

A pointer to an interface reference function that is implemented by the display port driver.

### -field InterfaceDereference

A pointer to an interface dereference function that is implemented by the display port driver.

### -field AgpAllocatePool

A pointer to the display port driver's [**AgpAllocatePool**](nc-dispmprt-dxgkcb_agp_allocate_pool.md) function.

### -field AgpFreePool

A pointer to the display port driver's [**AgpFreePool**](nc-dispmprt-dxgkcb_agp_free_pool.md) function.

### -field AgpSetCommand

A pointer to the display port driver's [**AgpSetCommand**](nc-dispmprt-dxgkcb_agp_set_command.md) function.

## -remarks

The display miniport driver supplies the **Size** and **Version** members of this structure, and then calls [**DxgkCbQueryServices**](nc-dispmprt-dxgkcb_query_services.md), which fills in the remaining members of this structure.
