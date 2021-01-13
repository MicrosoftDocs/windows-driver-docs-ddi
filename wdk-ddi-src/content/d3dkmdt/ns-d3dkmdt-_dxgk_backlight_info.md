---
UID: NS:d3dkmdt._DXGK_BACKLIGHT_INFO
title: _DXGK_BACKLIGHT_INFO (d3dkmdt.h)
description: Contains the current level of backlight reduction that is applied to the integrated display panel. Used by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers that support adaptive brightness control.
old-location: display\dxgk_backlight_info.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGK_BACKLIGHT_INFO structure"]
ms.keywords: DXGK_BACKLIGHT_INFO, DXGK_BACKLIGHT_INFO structure [Display Devices], _DXGK_BACKLIGHT_INFO, d3dkmdt/DXGK_BACKLIGHT_INFO, display.dxgk_backlight_info
req.header: d3dkmdt.h
req.include-header:
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
req.typenames: DXGK_BACKLIGHT_INFO
f1_keywords:
 - _DXGK_BACKLIGHT_INFO
 - d3dkmdt/_DXGK_BACKLIGHT_INFO
 - DXGK_BACKLIGHT_INFO
 - d3dkmdt/DXGK_BACKLIGHT_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmdt.h
api_name:
 - DXGK_BACKLIGHT_INFO
---

# _DXGK_BACKLIGHT_INFO structure


## -description

Contains the current level of backlight reduction that is applied to the integrated display panel. Used by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers that support adaptive brightness control.

## -struct-fields

### -field BacklightUsersetting

[out] The absolute brightness level in hardware that corresponds to the current percent brightness level requested by the operating system.

This member can range in value from 0 to 65535.

### -field BacklightEffective

[out] The absolute brightness level in hardware that is currently set by the display miniport drive for adaptive brightness control.

This member can range in value from 0 to 65535.

### -field GammaRamp

[out] A <a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_gamma_ramp_rgb256x3x16">D3DDDI_GAMMA_RAMP_RGB256x3x16</a> structure that contains a description of a gamma lookup table.
This lookup table represents the gamma ramp that has been optimized for backlight display by the display miniport driver from a gamma ramp set by an application.

## -remarks

For more information about the use of this structure, see Remarks of the <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgk_brightness_get_backlight_reduction">DxgkDdiGetBacklightReduction</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_gamma_ramp_rgb256x3x16">D3DDDI_GAMMA_RAMP_RGB256x3x16</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgk_brightness_get_backlight_reduction">DxgkDdiGetBacklightReduction</a>
