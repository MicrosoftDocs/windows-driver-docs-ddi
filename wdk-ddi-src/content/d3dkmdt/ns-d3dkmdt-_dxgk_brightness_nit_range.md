---
UID: NS:d3dkmdt._DXGK_BRIGHTNESS_NIT_RANGE
title: _DXGK_BRIGHTNESS_NIT_RANGE
author: windows-driver-content
description: This structure represents a linear range of supported millinit levels.
ms.assetid: 39ca173d-97a6-4eb3-bb6c-436801c56d1b
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGK_BRIGHTNESS_NIT_RANGE, DXGK_BRIGHTNESS_NIT_RANGE,
req.header: d3dkmdt.h
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
req.typenames: DXGK_BRIGHTNESS_NIT_RANGE
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	_DXGK_BRIGHTNESS_NIT_RANGE
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGK_BRIGHTNESS_NIT_RANGE structure

## -description

This structure represents a linear range of supported millinit levels. If the driver has not set [DXGK_BRIGHTNESS_CAPS.NitsBrightness](ns-d3dkmdt-_dxgk_brightness_caps.md), then all values represent brightness level in uncalibrated thousandths of a percent. 

## -struct-fields

### -field MinimumLevelMillinit

Lowest level in this range.  Calibrated data provided to the Display Driver by OEMs should be taken with an On Pixel Ratio (OPR) percentage of 100% where each pixel is set to an RGB value of (255, 255, 255) or floating point equivalent.

### -field MaximumLevelMillinit

Highest level in this range. Can be equal to MinimumLevelMillinit to represent a range with just one level. For example, this could support a display with just one boost level. Calibrated data provided to the Display Driver by OEMs should be taken with an On Pixel Ratio (OPR) percentage of 100% where each pixel is set to an RGB value of (255, 255, 255) or floating point equivalent.

### -field StepSizeMillinit

The size of steps between valid brightness levels in the range. Minimum + StepSize * n is considered a valid level for non-negative n, where the level is equal to or below maximum. (Maximum – Minimum) % StepSize should always be zero. If MinimumLevelMillinit == MaximumLevelMillinit, then this should be zero.

