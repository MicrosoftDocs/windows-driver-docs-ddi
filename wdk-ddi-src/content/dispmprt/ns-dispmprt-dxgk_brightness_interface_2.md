---
UID: NS:dispmprt.__unnamed_struct_1
title: DXGK_BRIGHTNESS_INTERFACE_2 (dispmprt.h)
description: Contains pointers to functions in the Panel Brightness Control Interface Version 2. Used by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers that support adaptive and smooth brightness control.
old-location: display\dxgk_brightness_interface_2.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGK_BRIGHTNESS_INTERFACE_2 structure"]
ms.keywords: "*PDXGK_BRIGHTNESS_INTERFACE_2, DXGK_BRIGHTNESS_INTERFACE_2, DXGK_BRIGHTNESS_INTERFACE_2 structure [Display Devices], PDXGK_BRIGHTNESS_INTERFACE_2, PDXGK_BRIGHTNESS_INTERFACE_2 structure pointer [Display Devices], display.dxgk_brightness_interface_2, dispmprt/DXGK_BRIGHTNESS_INTERFACE_2, dispmprt/PDXGK_BRIGHTNESS_INTERFACE_2"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.typenames: DXGK_BRIGHTNESS_INTERFACE_2, *PDXGK_BRIGHTNESS_INTERFACE_2
f1_keywords:
 - PDXGK_BRIGHTNESS_INTERFACE_2
 - dispmprt/PDXGK_BRIGHTNESS_INTERFACE_2
 - DXGK_BRIGHTNESS_INTERFACE_2
 - dispmprt/DXGK_BRIGHTNESS_INTERFACE_2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Dispmprt.h
api_name:
 - PDXGK_BRIGHTNESS_INTERFACE_2
 - DXGK_BRIGHTNESS_INTERFACE_2
---

# DXGK_BRIGHTNESS_INTERFACE_2 structure


## -description

Contains pointers to functions in the Panel Brightness Control Interface Version 2. Used by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers that support adaptive and smooth brightness control.

## -struct-fields

### -field Size

[in] The size, in bytes, of this structure.

### -field Version

[in] The version number of the brightness interface. Version number constants are defined in Dispmprt.h (for example, <b>DXGK_BRIGHTNESS_INTERFACE_VERSION_2</b>).

### -field Context

[in] A pointer to a private context block.

### -field InterfaceReference

[out] A pointer to an interface reference function that is implemented by the display miniport driver.

### -field InterfaceDereference

[out] A pointer to an interface dereference function that is implemented by the display miniport driver.

### -field GetPossibleBrightness

[out] A pointer to the display miniport driver's <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgk_brightness_get_possible">DxgkDdiGetPossibleBrightness</a> function.

### -field SetBrightness

[out] A pointer to the display miniport driver's <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgk_brightness_set">DxgkDdiSetBrightness</a> function.

### -field GetBrightness

[out] A pointer to the display miniport driver's <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgk_brightness_get">DxgkDdiGetBrightness</a> function.

### -field GetBrightnessCaps

[out] A pointer to the display miniport driver's <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgk_brightness_get_caps">DxgkDdiGetBrightnessCaps</a> function. This function is available starting with Windows 8.

### -field SetBrightnessState

[out] A pointer to the display miniport driver's  <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgk_brightness_set_state">DxgkDdiSetBrightnessState</a> function. This function is available starting with Windows 8.

### -field SetBacklightOptimization

[out] A pointer to the display miniport driver's  <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgk_brightness_set_backlight_optimization">DxgkDdiSetBacklightOptimization</a> function. This function is available starting with Windows 8.

### -field GetBacklightReduction

[out] A pointer to the display miniport driver's  <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgk_brightness_get_backlight_reduction">DxgkDdiGetBacklightReduction</a> function. This function is available starting with Windows 8.

## -remarks

This structure provides additional members, beyond those in the <a href="/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-dxgk_brightness_interface">DXGK_BRIGHTNESS_INTERFACE</a> interface, that point to driver-implemented functions that control, measure, and optimize display panel brightness and allow smooth brightness control.

For more information on this interface, see <a href="/windows-hardware/drivers/ddi/index">Brightness Control Interface V. 2 (Adaptive and Smooth Brightness Control)</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-dxgk_brightness_interface">DXGK_BRIGHTNESS_INTERFACE</a>

