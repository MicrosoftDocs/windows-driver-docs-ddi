---
UID: NS:dispmprt._DXGK_DIAGNOSTIC_PSR
title: _DXGK_DIAGNOSTIC_PSR (dispmprt.h)
description: A diagnostic that indicates that the panel connected via the target in the TargetId field in the _DXGK_DIAGNOSTIC_HEADER structure has entered or exited a panel self-refresh (PSR) state.
ms.assetid: ec746886-9f49-4986-a73e-4a806f8e5025
ms.date: 10/19/2018
keywords: ["_DXGK_DIAGNOSTIC_PSR structure"]
f1_keywords:
 - "dispmprt/_DXGK_DIAGNOSTIC_PSR"
 - "_DXGK_DIAGNOSTIC_PSR"
ms.keywords: _DXGK_DIAGNOSTIC_PSR, DXGK_DIAGNOSTIC_PSR,
req.header: dispmprt.h
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
req.typenames: DXGK_DIAGNOSTIC_PSR
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- dispmprt.h
api_name:
- _DXGK_DIAGNOSTIC_PSR
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGK_DIAGNOSTIC_PSR structure

## -description

A diagnostic that indicates that the panel connected via the target in the *TargetId* field in the [_DXGK_DIAGNOSTIC_HEADER](ns-dispmprt-_dxgk_diagnostic_header.md) structure has entered or exited a panel self-refresh (PSR) state.

## -struct-fields

### -field RefreshReason

A set of bit-fields indicating the reason or reasons for exiting PSR or, if none is set, indicates that the target is entering PSR.

### -field RefreshReason.Present

Pixels in one or more planes have been modified, requiring that the display be updated. This could be that the pixel data has changed or a change to MPO visibility, position, scaling, orientation or some combination of these.

### -field RefreshReason.CursorUpdate

The cursor image, position, visibility or a combination of these have been updated.

### -field RefreshReason.VSyncEnabled

Vsync interrupts have been enabled and the hardware requires scan out to be driven in order to generate the Vsync interrupt.

### -field RefreshReason.ColorTransformationChange

Any form of color transform that is being applied requires the pixels on the panel to be updated. This could be any one of: legacy gamma, DXGI gamma, the 3x4 matrix color transform or any newer form of color transform.

### -field RefreshReason.BrightnessChange

The display brightness has been changed and based on the hardware/display technology, this requires refreshing the pixels in the panel.
>**Note** For a display using a backlight, a brightness change would only require leaving PSR if backlight optimizations mean that the pixels also need to be updated.

### -field RefreshReason.SinkRequest

The display panel has requested an update from the host.

### -field RefreshReason.Other

A reason understood by the driver but not specified by any of the above. Ideally, a new flag should be defined for any such reason in the next release.

### -field RefreshReason.Reserved

Reserved.

### -field Value

Value of the PSR.

### -field Header

A [DXGK_DIAGNOSTIC_HEADER](ns-dispmprt-_dxgk_diagnostic_header.md) structure that indicates what kind of diagnostic is being reported.

## -remarks

When the panel enters self-refresh, the driver should send this diagnostic with none of the bit-fields set in the *RefreshReason* field.

When the panel needs to exit self-refresh to update the content, the driver should send this diagnostic with at least one of the bit-fields within RefreshReason, indicating the reason(s) for exiting PSR. If multiple factors caused PSR to be exited, the driver should attempt to set all appropriate bit-field reasons. However, it is more important that flags should not be set if the reason was not the trigger to exit PSR, than it is to capture all the reasons which did trigger the exit. This is because once PSR has been exited, the driver should not subsequently report additional reasons that PSR would have been exited so under reporting is valid, as long as at least one reason is provided.

If the panel and driver support PSR2, where updates do not require a full frame to be sent to the panel in order to refresh a smaller portion, such updates should still be reported to the OS while exiting PSR. For example, if the display is in PSR and the cursor shape is changed without any other updates, the driver should be able to send a small fraction of the full frame of pixels, likely only the lines containing the cursor. In this case, the driver should still report that PSR has been exited, with reason *CursorUpdate*. In a later release, extra diagnostic fields may be added to distinguish partial and full updates.
