---
UID: NS:dispmprt.__unnamed_struct_2
title: DXGK_BRIGHTNESS_INTERFACE_3
author: windows-driver-content
description:
ms.assetid: eccaf527-4b7b-4ebb-a2ab-e4d94a1d357d
ms.date: 10/19/2018
ms.topic: struct
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
-	apiref
api_type:
-	HeaderDef
api_location:
-	dispmprt.h
api_name:
-	DXGK_BRIGHTNESS_INTERFACE_3
product: 
-	Windows
targetos: Windows
---

# DXGK_BRIGHTNESS_INTERFACE_3 structure

## -description

Contains pointers to functions in the Panel Brightness Control Interface Version 3. Used by Windows Display Driver Model (WDDM) 2.4 and later display miniport drivers that supports multiple displays that can be set to calibrated nit-based brightness levels.

## -struct-fields

### -field Size

[in] The size, in bytes, of this structure.

### -field Version

[in] The version number of the brightness interface. Version number constants are defined in Dispmprt.h.

### -field Context

[out] A pointer to a private context block.

### -field InterfaceReference

[out] A pointer to an interface reference function that is implemented by the display miniport driver.

### -field InterfaceDereference

[out] A pointer to an interface dereference function that is implemented by the display miniport driver.

### -field SetBrightness

[out] A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_set_3.md">DxgkDdiSetBrightness3</a> function.

### -field GetBrightness

[out] A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_get_3.md">DxgkDdiGetBrightness3</a> function.

### -field GetBrightnessCaps

[out] A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_get_caps_3.md">DxgkDdiGetBrightnessCaps3</a> function. This function is available starting with Windows 10.

### -field GetNitRanges

[out] A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_get_nit_ranges.md">DxgkDdiGetNitRanges</a> function. This function is available starting with Windows 10.

### -field SetBacklightOptimization

[out] A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_set_backlight_optimization_3.md">DxgkBrightnessSetBacklightOptimization3</a> function. This function is available starting with Windows 10.
