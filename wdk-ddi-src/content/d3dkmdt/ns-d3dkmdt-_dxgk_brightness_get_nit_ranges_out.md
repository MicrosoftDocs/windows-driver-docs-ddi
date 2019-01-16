---
UID: NS:d3dkmdt._DXGK_BRIGHTNESS_GET_NIT_RANGES_OUT
title: "_DXGK_BRIGHTNESS_GET_NIT_RANGES_OUT"
description: Contains the output parameters for the DxgkBrightnessGetNitRanges callback function.
ms.assetid: a63d2e7b-ce96-4ac4-a918-2649280fc421
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _DXGK_BRIGHTNESS_GET_NIT_RANGES_OUT, *PDXGK_BRIGHTNESS_GET_NIT_RANGES_OUT, DXGK_BRIGHTNESS_GET_NIT_RANGES_OUT,
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
req.typenames: DXGK_BRIGHTNESS_GET_NIT_RANGES_OUT, *PDXGK_BRIGHTNESS_GET_NIT_RANGES_OUT
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	_DXGK_BRIGHTNESS_GET_NIT_RANGES_OUT
product:
-	Windows
targetos: Windows
tech.root: display
---

# _DXGK_BRIGHTNESS_GET_NIT_RANGES_OUT structure

## -description

Contains the output parameters for the [DxgkBrightnessGetNitRanges](..\dispmprt\nc-dispmprt-dxgk_brightness_get_nit_ranges.md) callback function.

## -struct-fields

### -field NormalRangeCount

The number of ranges that are not boost level ranges.

### -field RangeCount

The number of supported ranges, including boost level ranges.

### -field PreferredMaximumBrightness

An OEM-preferred level to correspond with 100% brightness. If there is no OEM preference, the value should be zero.

### -field SupportedRanges

A list of supported ranges. Ranges should be in strictly increasing order by brightness, with normal ranges coming before boost ranges.

