---
UID: NS:dispmprt._DXGK_MIRACAST_INTERFACE
title: _DXGK_MIRACAST_INTERFACE (dispmprt.h)
description: Contains pointers to functions in the Wireless display (Miracast) interface that the display miniport driver implements to create, destroy, query, and control Miracast device resources.
old-location: display\dxgk_miracast_display_interface.htm
tech.root: display
ms.date: 10/12/2018
keywords: ["DXGK_MIRACAST_INTERFACE structure"]
ms.keywords: "*PDXGK_MIRACAST_DISPLAY_INTERFACE, DXGK_MIRACAST_DISPLAY_INTERFACE, DXGK_MIRACAST_DISPLAY_INTERFACE structure [Display Devices], PDXGK_MIRACAST_DISPLAY_INTERFACE, PDXGK_MIRACAST_DISPLAY_INTERFACE structure pointer [Display Devices], _DXGK_MIRACAST_INTERFACE, display.dxgk_miracast_display_interface, dispmprt/DXGK_MIRACAST_DISPLAY_INTERFACE, dispmprt/PDXGK_MIRACAST_DISPLAY_INTERFACE"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.typenames: DXGK_MIRACAST_DISPLAY_INTERFACE, *PDXGK_MIRACAST_DISPLAY_INTERFACE
f1_keywords:
 - _DXGK_MIRACAST_INTERFACE
 - dispmprt/_DXGK_MIRACAST_INTERFACE
 - PDXGK_MIRACAST_DISPLAY_INTERFACE
 - dispmprt/PDXGK_MIRACAST_DISPLAY_INTERFACE
 - DXGK_MIRACAST_DISPLAY_INTERFACE
 - dispmprt/DXGK_MIRACAST_DISPLAY_INTERFACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Dispmprt.h
api_name:
 - DXGK_MIRACAST_DISPLAY_INTERFACE
---

# _DXGK_MIRACAST_INTERFACE structure


## -description

Contains pointers to functions in the [Wireless display (Miracast) interface](/windows-hardware/drivers/display/wireless-displays--miracast-#miracast-reference) that the display miniport driver implements to create, destroy, query, and control Miracast device resources.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Version

The version number of the Miracast interface. Version number constants are defined in Dispmprt.h (for example, DXGK_MIRACAST_DISPLAY_INTERFACE_VERSION_1).

### -field Context

A pointer to a context that is provided by the display miniport driver.

### -field InterfaceReference

A pointer to an interface reference function that is implemented by the display miniport driver.

### -field InterfaceDereference

A pointer to an interface dereference function that is implemented by the display miniport driver.

### -field DxgkDdiMiracastQueryCaps

A pointer to the display miniport driver's [DxgkDdiMiracastQueryCaps](nc-dispmprt-dxgkddi_miracast_query_caps.md) function.

### -field DxgkDdiMiracastCreateContext

A pointer to the display miniport driver's [DxgkDdiMiracastCreateContext](nc-dispmprt-dxgkddi_miracast_create_context.md) function.

### -field DxgkDdiMiracastIoControl

A pointer to the display miniport driver's [DxgkDdiMiracastIoControl](nc-dispmprt-dxgkddi_miracast_handle_io_control.md) function.

### -field DxgkDdiMiracastDestroyContext

A pointer to the display miniport driver's [DxgkDdiMiracastDestroyContext](nc-dispmprt-dxgkddi_miracast_destroy_context.md) function.

## -remarks

When the graphics adapter is started, the Microsoft DirectX graphics kernel subsystem calls the display miniport driver's [DxgkDdiQueryInterface](nc-dispmprt-dxgkddi_query_interface.md) function to retrieve the interface.

If the driver does not support Miracast displays, it should fail the query for this interface.

If the driver supports Miracast displays, then it must also support High-bandwidth Digital Content Protection (HDCP).

For more info on how to use the Miracast interface, see [WDDM display miniport driver tasks to support Miracast wireless displays](/windows-hardware/drivers/display/wddm-display-miniport-driver-tasks-to-support-miracast-wireless-displays).

## -see-also

[DxgkDdiMiracastCreateContext](nc-dispmprt-dxgkddi_miracast_create_context.md)



[DxgkDdiMiracastDestroyContext](nc-dispmprt-dxgkddi_miracast_destroy_context.md)



[DxgkDdiMiracastIoControl](nc-dispmprt-dxgkddi_miracast_handle_io_control.md)




[DxgkDdiMiracastQueryCaps](nc-dispmprt-dxgkddi_miracast_query_caps.md)



[DxgkDdiQueryInterface](nc-dispmprt-dxgkddi_query_interface.md)
