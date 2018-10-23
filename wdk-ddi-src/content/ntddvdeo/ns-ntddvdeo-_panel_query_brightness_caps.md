---
UID: NS:ntddvdeo._PANEL_QUERY_BRIGHTNESS_CAPS
title: _PANEL_QUERY_BRIGHTNESS_CAPS
author: windows-driver-content
description: Retrieves brightness control capabilities of a display panel.
tech.root: display
ms.assetid: b0bdacef-4409-49cf-b53b-6e7023617793
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _PANEL_QUERY_BRIGHTNESS_CAPS, *PPANEL_QUERY_BRIGHTNESS_CAPS, PANEL_QUERY_BRIGHTNESS_CAPS
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
req.typenames: PANEL_QUERY_BRIGHTNESS_CAPS, *PPANEL_QUERY_BRIGHTNESS_CAPS
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	ntddvdeo.h
api_name:
-	_PANEL_QUERY_BRIGHTNESS_CAPS
product: 
-	Windows
targetos: Windows
---

# _PANEL_QUERY_BRIGHTNESS_CAPS structure

## -description

Retrieves brightness control capabilities of a display panel.

## -struct-fields

### -field Smooth

All drivers are required to support a smooth timed transition.

### -field Adaptive

Supports adaptive transition.

### -field NitsCalibrated

The display brightness is calibrated to correspond to absolute brightness levels measured in nits. Calibrated data provided to the Display Driver by OEMs should be taken with an On Pixel Ratio (OPR) percentage of 100% where each pixel is set to an RGB value of (255, 255, 255) or floating point equivalent. If it is not set, then the OS is aware that the levels exposed by GetNitRanges do not necessarily represent the actual luminance of the display.

### -field Reserved

Reserved.

### -field Value

Value.

### -field Version

The target version. This value should always be DXGK_BRIGHTNESS_INTERFACE_VERSION_3.
