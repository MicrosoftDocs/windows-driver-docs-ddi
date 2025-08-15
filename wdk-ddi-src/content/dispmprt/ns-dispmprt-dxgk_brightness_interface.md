---
UID: NS:dispmprt.DXGK_BRIGHTNESS_INTERFACE
title: DXGK_BRIGHTNESS_INTERFACE (dispmprt.h)
description: The DXGK_BRIGHTNESS_INTERFACE structure contains pointers to functions in the Panel Brightness Control Interface, which is implemented by the display miniport driver.
tech.root: display
ms.date: 08/15/2025
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
req.typenames: DXGK_BRIGHTNESS_INTERFACE, *PDXGK_BRIGHTNESS_INTERFACE
f1_keywords:
 - PDXGK_BRIGHTNESS_INTERFACE
 - dispmprt/PDXGK_BRIGHTNESS_INTERFACE
 - DXGK_BRIGHTNESS_INTERFACE
 - dispmprt/DXGK_BRIGHTNESS_INTERFACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - PDXGK_BRIGHTNESS_INTERFACE
 - DXGK_BRIGHTNESS_INTERFACE
---

# DXGK_BRIGHTNESS_INTERFACE structure

## -description

The **DXGK_BRIGHTNESS_INTERFACE** structure contains pointers to the kernel-mode display driver's (KMD) functions for Version 1 of the Panel Brightness Control Interface.

## -struct-fields

### -field Size

[in] The size, in bytes, of this structure.

### -field Version

[in] The version number of the brightness interface. Must be **DXGK_BRIGHTNESS_INTERFACE_VERSION_1** for this structure. Version number constants are defined in *Dispmprt.h*.

### -field Context

[out] A pointer to a private context block.

### -field InterfaceReference

[out] A pointer to an interface reference function that is implemented by the KMD.

### -field InterfaceDereference

[out] A pointer to an interface dereference function that is implemented by the KMD.

### -field GetPossibleBrightness

[out] A pointer to the KMD's [DxgkDdiGetPossibleBrightness](nc-dispmprt-dxgk_brightness_get_possible.md) function.

### -field SetBrightness

[out] A pointer to the KMD's [DxgkDdiSetBrightness](nc-dispmprt-dxgk_brightness_set.md) function.

### -field GetBrightness

[out] A pointer to the KMD's [DxgkDdiGetBrightness](nc-dispmprt-dxgk_brightness_get.md) function.

## -remarks

A kernel-mode component such as *Dxgkrnl* that must use the brightness interface initiates a call to the KMD's [DxgkDdiQueryInterface](nc-dispmprt-dxgkddi_query_interface.md) function to retrieve the interface and passes a GUID_DEVINTERFACE_BRIGHTNESS in the **InterfaceType** member of the [QUERY_INTERFACE](/windows-hardware/drivers/ddi/video/ns-video-_query_interface) structure that the **QueryInterface** parameter points to.

For more information, see [Supporting brightness controls on integrated display panels](https://learn.microsoft.com/windows-hardware/drivers/display/supporting-brightness-controls-on-integrated-display-panels).

## -see-also

[DXGK_BRIGHTNESS_INTERFACE_3](ns-dispmprt-dxgk_brightness_interface_3.md)

[DXGK_BRIGHTNESS_INTERFACE_2](ns-dispmprt-dxgk_brightness_interface_2.md)

[DxgkDdiGetBrightness](nc-dispmprt-dxgk_brightness_get.md)

[DxgkDdiGetPossibleBrightness](nc-dispmprt-dxgk_brightness_get_possible.md)

[DxgkDdiQueryInterface](nc-dispmprt-dxgkddi_query_interface.md)

[DxgkDdiSetBrightness](nc-dispmprt-dxgk_brightness_set.md)

[QUERY_INTERFACE](/windows-hardware/drivers/ddi/video/ns-video-_query_interface)
