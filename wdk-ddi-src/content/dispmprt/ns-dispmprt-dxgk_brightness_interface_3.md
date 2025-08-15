---
UID: NS:dispmprt.DXGK_BRIGHTNESS_INTERFACE_3
title: DXGK_BRIGHTNESS_INTERFACE_3 (dispmprt.h)
description: "Learn more about: DXGK_BRIGHTNESS_INTERFACE_3 structure"
ms.date: 08/14/2025
req.header: dispmprt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGK_BRIGHTNESS_INTERFACE_3, *PDXGK_BRIGHTNESS_INTERFACE_3
targetos: Windows
tech.root: display
f1_keywords:
 - "dispmprt/DXGK_BRIGHTNESS_INTERFACE_3"
 - "DXGK_BRIGHTNESS_INTERFACE_3"
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - DXGK_BRIGHTNESS_INTERFACE_3
---

## -description

The **DXGK_BRIGHTNESS_INTERFACE_3** structure contains pointers to the kernel-mode display driver's (KMD) functions for Version 3 of the Panel Brightness Control Interface.

## -struct-fields

### -field Size [in]

The size, in bytes, of this structure.

### -field Version [in]

The version number of the brightness interface. Must be set to **DXGK_BRIGHTNESS_INTERFACE_VERSION_3**. Version number constants are defined in *Dispmprt.h*.

### -field Context [out]

A pointer to a private context block.

### -field InterfaceReference [out]

A pointer to an interface reference function that is implemented by the KMD.

### -field InterfaceDereference [out]

A pointer to an interface dereference function that is implemented by the KMD.

### -field SetBrightness [out]

A pointer to the KMD's [DxgkDdiSetBrightness3](nc-dispmprt-dxgk_brightness_set_3.md) function.

### -field GetBrightness [out]

A pointer to the KMD's [DxgkDdiGetBrightness3](nc-dispmprt-dxgk_brightness_get_3.md) function.

### -field GetBrightnessCaps [out]

A pointer to the KMD's [DxgkDdiGetBrightnessCaps3](nc-dispmprt-dxgk_brightness_get_caps_3.md) function. This function is available starting with Windows 10.

### -field GetNitRanges [out]

A pointer to the KMD's [DxgkDdiGetNitRanges](nc-dispmprt-dxgk_brightness_get_nit_ranges.md) function. This function is available starting with Windows 10.

### -field SetBacklightOptimization [out]

A pointer to the KMD's [DxgkBrightnessSetBacklightOptimization3](nc-dispmprt-dxgk_brightness_set_backlight_optimization_3.md) function. This function is available starting with Windows 10.

## -remarks

Version 3 is used by Windows Display Driver Model (WDDM) 2.4 and later KMDs that support multiple displays that can be set to calibrated nit-based brightness levels.

A kernel-mode component such as *Dxgkrnl* that must use the brightness interface initiates a call to the KMD's [DxgkDdiQueryInterface](nc-dispmprt-dxgkddi_query_interface.md) function to retrieve the interface and passes a GUID_DEVINTERFACE_BRIGHTNESS_3 in the **InterfaceType** member of the [QUERY_INTERFACE](/windows-hardware/drivers/ddi/video/ns-video-_query_interface) structure that the **QueryInterface** parameter points to.

For more information, see [Supporting brightness controls on integrated display panels](https://learn.microsoft.com/windows-hardware/drivers/display/supporting-brightness-controls-on-integrated-display-panels).

## -see-also

[DXGK_BRIGHTNESS_INTERFACE_2](ns-dispmprt-dxgk_brightness_interface_2.md)

[DXGK_BRIGHTNESS_INTERFACE](ns-dispmprt-dxgk_brightness_interface.md)

[DxgkDdiGetBrightness3](nc-dispmprt-dxgk_brightness_get_3.md)

[DxgkDdiGetPossibleBrightness](nc-dispmprt-dxgk_brightness_get_possible.md)

[DxgkddiQueryInterface](nc-dispmprt-dxgkddi_query_interface.md)

[DxgkDdiSetBrightness3](nc-dispmprt-dxgk_brightness_set_3.md)

[QUERY_INTERFACE](/windows-hardware/drivers/ddi/video/ns-video-_query_interface)
