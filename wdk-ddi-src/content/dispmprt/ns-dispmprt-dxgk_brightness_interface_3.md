---
UID: NS:dispmprt.__unnamed_struct_2
title: DXGK_BRIGHTNESS_INTERFACE_3 (dispmprt.h)
description: "Learn more about: DXGK_BRIGHTNESS_INTERFACE_3 structure"
ms.date: 09/23/2022
keywords: ["DXGK_BRIGHTNESS_INTERFACE_3 structure"]
f1_keywords:
 - "dispmprt/DXGK_BRIGHTNESS_INTERFACE_3"
 - "DXGK_BRIGHTNESS_INTERFACE_3"
ms.keywords: DXGK_BRIGHTNESS_INTERFACE_3, *PDXGK_BRIGHTNESS_INTERFACE_3, DXGK_BRIGHTNESS_INTERFACE_3,
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
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- dispmprt.h
api_name:
- DXGK_BRIGHTNESS_INTERFACE_3
product: 
- Windows
targetos: Windows
tech.root: display
---

## -description

Contains pointers to functions in the Panel Brightness Control Interface Version 3. Used by Windows Display Driver Model (WDDM) 2.4 and later display miniport drivers that supports multiple displays that can be set to calibrated nit-based brightness levels.

## -struct-fields

### -field Size [in]

The size, in bytes, of this structure.

### -field Version [in]

The version number of the brightness interface. Version number constants are defined in Dispmprt.h.

### -field Context [out]

A pointer to a private context block.

### -field InterfaceReference [out]

A pointer to an interface reference function that is implemented by the display miniport driver.

### -field InterfaceDereference [out]

A pointer to an interface dereference function that is implemented by the display miniport driver.

### -field SetBrightness [out]

A pointer to the display miniport driver's [DxgkDdiSetBrightness3](..\dispmprt\nc-dispmprt-dxgk_brightness_set_3.md) function.

### -field GetBrightness [out]

A pointer to the display miniport driver's [DxgkDdiGetBrightness3](..\dispmprt\nc-dispmprt-dxgk_brightness_get_3.md) function.

### -field GetBrightnessCaps [out]

A pointer to the display miniport driver's [DxgkDdiGetBrightnessCaps3](..\dispmprt\nc-dispmprt-dxgk_brightness_get_caps_3.md) function. This function is available starting with Windows 10.

### -field GetNitRanges [out]

A pointer to the display miniport driver's [DxgkDdiGetNitRanges](..\dispmprt\nc-dispmprt-dxgk_brightness_get_nit_ranges.md) function. This function is available starting with Windows 10.

### -field SetBacklightOptimization [out]

A pointer to the display miniport driver's [DxgkBrightnessSetBacklightOptimization3](..\dispmprt\nc-dispmprt-dxgk_brightness_set_backlight_optimization_3.md) function. This function is available starting with Windows 10.
