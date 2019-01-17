---
UID: NS:ntddvdeo._PANEL_GET_BRIGHTNESS
title: _PANEL_GET_BRIGHTNESS
description: Gets the current brightness level, plus details on the brightness transition in progress.
tech.root: display
ms.assetid: f7fbdbb4-f3cc-4ab7-b891-370190a96c19
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _PANEL_GET_BRIGHTNESS, PANEL_GET_BRIGHTNESS, *PPANEL_GET_BRIGHTNESS,
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
req.typenames: PANEL_GET_BRIGHTNESS, *PPANEL_GET_BRIGHTNESS
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	ntddvdeo.h
api_name:
-	_PANEL_GET_BRIGHTNESS
product: 
- Windows
targetos: Windows
---

# _PANEL_GET_BRIGHTNESS structure

## -description

Gets the current brightness level, plus details on the brightness transition in progress.

## -struct-fields

### -field CurrentInMillinits

Current brightness level.

### -field TargetInMillinits

The brightness level to transition to.

### -field Level

The brightness level.

### -field Version

The target version. This value should always be DXGK_BRIGHTNESS_INTERFACE_VERSION_3.

