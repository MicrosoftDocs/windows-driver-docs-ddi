---
UID: NS:ntddvdeo._PANEL_SET_BRIGHTNESS
title: _PANEL_SET_BRIGHTNESS (ntddvdeo.h)
description: Directs the driver to linearly ramp the brightness from its current brightness level to a target brightness level over a specified length of time.
tech.root: display
ms.assetid: d16d02f1-de69-4224-9e52-3ce78dcc63f3
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "ntddvdeo/_PANEL_SET_BRIGHTNESS"
ms.keywords: _PANEL_SET_BRIGHTNESS, *PPANEL_SET_BRIGHTNESS, PANEL_SET_BRIGHTNESS,
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
req.typenames: PANEL_SET_BRIGHTNESS, *PPANEL_SET_BRIGHTNESS
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- ntddvdeo.h
api_name:
- _PANEL_SET_BRIGHTNESS
product: 
- Windows
targetos: Windows
---

# _PANEL_SET_BRIGHTNESS structure

## -description

Directs the driver to linearly ramp the brightness from its current brightness level to a target brightness level over a specified length of time.

## -struct-fields

### -field Millinits

The brightness level in millinits to transition to.

### -field TransitionTimeInMs

How long the transition should take.

### -field SensorData

Contains sensor readings the driver can use to determine the best way to achieve the desired brightness under current lighting conditions. Not all devices will support all or any sensor readings, and the driver should not fail if any are missing.

### -field Level

The optimization level of brightness control.

### -field Version

The target version. This value should always be DXGK_BRIGHTNESS_INTERFACE_VERSION_3.

