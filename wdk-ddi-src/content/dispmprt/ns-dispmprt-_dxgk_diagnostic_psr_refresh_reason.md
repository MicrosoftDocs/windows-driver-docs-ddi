---
UID: NS:dispmprt._DXGK_DIAGNOSTIC_PSR_REFRESH_REASON
title: _DXGK_DIAGNOSTIC_PSR_REFRESH_REASON
author: windows-driver-content
description: Indicates the reason or reasons for exiting PSR (Panel Self-Refresh).
ms.assetid: 6dcc76d1-6019-4ccd-b560-44ec3d59e0cd
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _DXGK_DIAGNOSTIC_PSR_REFRESH_REASON, DXGK_DIAGNOSTIC_PSR_REFRESH_REASON, 
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGK_DIAGNOSTIC_PSR_REFRESH_REASON
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	dispmprt.h
api_name: 
-	_DXGK_DIAGNOSTIC_PSR_REFRESH_REASON
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# _DXGK_DIAGNOSTIC_PSR_REFRESH_REASON structure

## -description

Indicates the reason or reasons for exiting PSR (Panel Self-Refresh).

## -struct-fields

### -field Present

Pixels in one or more planes have been modified, requiring that the display be updated.

### -field CursorUpdate

The cursor image, position, visibility or a combination of these have been updated.

### -field VSyncEnabled

Vsync interrupts have been enabled and the hardware requires scanout to be driven in order to generate the Vsync interrupt.

This could be any one of: legacy gamma, DXGI gamma, the 3x4 matrix color transform or any newer form of color transform.

### -field ColorTransformationChange

Any form of color transform is being applied which requires the pixels on the panel to be updated.

### -field BrightnessChange

The display brightness has been changed and based on the hardware/display technology, this requires refreshing the pixels in the panel.  Note, for a display using a backlight, a brightness change would only require leaving PSR if backlight optimizations mean that the pixels also need to be updated.

### -field SinkRequest

The display panel has requested an update from the host.

### -field Other

A reason understood by the driver but not specified by any of the above. 

### -field Reserved

Reserved.

### -field Value
 

## -remarks

See [_DXGK_DIAGNOSTIC_PSR](../dispmprt/ns-dispmprt-_dxgk_diagnostic_psr.md) structure, in the remarks section for more info about PSR.

## -see-also
