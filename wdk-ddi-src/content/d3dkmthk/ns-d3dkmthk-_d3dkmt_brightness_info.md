---
UID: NS:d3dkmthk._D3DKMT_BRIGHTNESS_INFO
title: _D3DKMT_BRIGHTNESS_INFO (d3dkmthk.h)
description: Contains information about the brightness of an integrated display panel.
old-location: display\d3dkmt_brightness_info.htm
ms.assetid: a620b0b2-85ce-4373-a50c-299d8ce7a91c
ms.date: 05/10/2018
keywords: ["_D3DKMT_BRIGHTNESS_INFO structure"]
ms.keywords: D3DKMT_BRIGHTNESS_INFO, D3DKMT_BRIGHTNESS_INFO structure [Display Devices], _D3DKMT_BRIGHTNESS_INFO, d3dkmthk/D3DKMT_BRIGHTNESS_INFO, display.d3dkmt_brightness_info
f1_keywords:
 - "d3dkmthk/D3DKMT_BRIGHTNESS_INFO"
 - "D3DKMT_BRIGHTNESS_INFO"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dkmthk.h
api_name:
- D3DKMT_BRIGHTNESS_INFO
targetos: Windows
tech.root: display
req.typenames: D3DKMT_BRIGHTNESS_INFO
---

# _D3DKMT_BRIGHTNESS_INFO structure


## -description


Contains information about the brightness of an integrated display panel.


## -struct-fields




### -field Type

A value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ne-d3dkmthk-_d3dkmt_brightness_info_type">D3DKMT_BRIGHTNESS_INFO_TYPE</a> that  indicates the type of brightness information to retrieve or set.


### -field PossibleLevels

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_brightness_possible_levels">D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS</a> structure that contains information about all possible brightness levels that the integrated display panel supports.


### -field Brightness

The current brightness level.


### -field BrightnessCaps

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgk_brightness_caps">DXGK_BRIGHTNESS_CAPS</a> structure that represents the brightness control capabilities of the integrated display panel.


### -field BrightnessState

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgk_brightness_state">DXGK_BRIGHTNESS_STATE</a> structure that represents the smooth brightness control capabilities of the integrated display panel.


### -field OptimizationLevel

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-dxgk_backlight_optimization_level">DXGK_BACKLIGHT_OPTIMIZATION_LEVEL</a> structure that represents the optimization level of brightness control.


### -field ReductionInfo

A value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgk_backlight_info">DXGK_BACKLIGHT_INFO</a> that provides the current absolute level of backlight reduction.


### -field VerboseLogging

A boolean value that indicates whether Event Tracing for Windows (ETW) logging of brightness information should be verbose.

### -field NitRanges

List of supported nit ranges.

### -field GetBrightnessMillinits

Queries the driver for the current brightness level, in millinits.

### -field SetBrightnessMillinits

Directs the driver to linearly ramp the brightness from its current brightness level to a target brightness level over a specified length of time.

### -field ChildUid

An integer that uniquely identifies the child device.

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ne-d3dkmthk-_d3dkmt_brightness_info_type">D3DKMT_BRIGHTNESS_INFO_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_brightness_possible_levels">D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgk_backlight_info">DXGK_BACKLIGHT_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-dxgk_backlight_optimization_level">DXGK_BACKLIGHT_OPTIMIZATION_LEVEL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgk_brightness_caps">DXGK_BRIGHTNESS_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgk_brightness_state">DXGK_BRIGHTNESS_STATE</a>
 

 

