---
UID: NS:d3dkmdt._DXGK_BRIGHTNESS_GET_NIT_RANGES_OUT
title: "_DXGK_BRIGHTNESS_GET_NIT_RANGES_OUT"
author: windows-driver-content
description:
ms.assetid: a63d2e7b-ce96-4ac4-a918-2649280fc421
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	_DXGK_BRIGHTNESS_GET_NIT_RANGES_OUT
product:
-	Windows
targetos: Windows
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

