---
UID: NS:ntddvdeo._BRIGHTNESS_NIT_RANGE
title: _BRIGHTNESS_NIT_RANGE (ntddvdeo.h)
description: A linear range of supported millinit levels.
tech.root: display
ms.assetid: fb6130d9-161a-4a9d-af61-9474e5583299
ms.date: 10/19/2018
keywords: ["BRIGHTNESS_NIT_RANGE structure"]
ms.keywords: _BRIGHTNESS_NIT_RANGE, BRIGHTNESS_NIT_RANGE, *PBRIGHTNESS_NIT_RANGE,
req.header: ntddvdeo.h
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
req.typenames: BRIGHTNESS_NIT_RANGE, *PBRIGHTNESS_NIT_RANGE
targetos: Windows
f1_keywords:
 - _BRIGHTNESS_NIT_RANGE
 - ntddvdeo/_BRIGHTNESS_NIT_RANGE
 - PBRIGHTNESS_NIT_RANGE
 - ntddvdeo/PBRIGHTNESS_NIT_RANGE
 - BRIGHTNESS_NIT_RANGE
 - ntddvdeo/BRIGHTNESS_NIT_RANGE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddvdeo.h
api_name:
 - _BRIGHTNESS_NIT_RANGE
product:
 - Windows
---

# _BRIGHTNESS_NIT_RANGE structure


## -description

A linear range of supported millinit levels.

## -struct-fields

### -field MinLevelInMillinit

Lowest level in this range. Calibrated data provided to the Display Driver by OEMs should be taken with an On Pixel Ratio (OPR) percentage of 100% where each pixel is set to an RGB value of (255, 255, 255) or floating point equivalent.

### -field MaxLevelInMillinit

Highest level in this range. Can be equal to MinimumLevelInMillinit to represent a range with just one level. For example, this could support a display with just one boost level.  Calibrated data provided to the Display Driver by OEMs should be taken with an On Pixel Ratio (OPR) percentage of 100% where each pixel is set to an RGB value of (255, 255, 255) or floating point equivalent.

### -field StepSizeInMillinit

The size of steps between valid brightness levels in the range. Minimum + StepSize * n is considered a valid level for non-negative n, where the level is equal to or below maximum. (Maximum – Minimum) % StepSize should always be zero. If MinimumLevelInMillinit == MaximumLevelInMillinit, then this should be zero.

