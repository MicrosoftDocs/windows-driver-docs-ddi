---
UID: NS:dispmprt._DXGK_DIAGNOSTIC_PSR
title: DXGK_DIAGNOSTIC_PSR (dispmprt.h)
description: A diagnostic that indicates that the panel connected via the target in the TargetId field in the _DXGK_DIAGNOSTIC_HEADER structure has entered or exited a panel self-refresh (PSR) state.
ms.date: 05/31/2022
keywords: ["DXGK_DIAGNOSTIC_PSR structure"]
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
targetos: Windows
tech.root: display
f1_keywords:
 - _DXGK_DIAGNOSTIC_PSR
 - dispmprt/_DXGK_DIAGNOSTIC_PSR
 - DXGK_DIAGNOSTIC_PSR
 - dispmprt/DXGK_DIAGNOSTIC_PSR
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_DIAGNOSTIC_PSR
 - DXGK_DIAGNOSTIC_PSR
---

# DXGK_DIAGNOSTIC_PSR structure

## -description

A diagnostic that indicates that the panel connected via the target in the *TargetId* field in the [**DXGK_DIAGNOSTIC_HEADER**](ns-dispmprt-_dxgk_diagnostic_header.md) structure has entered or exited a panel self-refresh (PSR) state.

## -struct-fields

### -field Header

A [**DXGK_DIAGNOSTIC_HEADER**](ns-dispmprt-_dxgk_diagnostic_header.md) structure that indicates what kind of diagnostic is being reported.

### -field RefreshReason

A set of [**DXGK_DIAGNOSTIC_PSR_REFRESH_REASON**](ns-dispmprt-_dxgk_diagnostic_psr_refresh_reason.md) bit-fields that indicate the reason or reasons for exiting PSR or, if none is set, indicates that the target is entering PSR.

### -field Value

Value of the PSR.

## -remarks

When the panel enters self-refresh, the driver should send this diagnostic with none of the bit-fields set in the *RefreshReason* field.

When the panel needs to exit self-refresh to update the content, the driver should send this diagnostic with at least one of the bit-fields within RefreshReason, indicating the reason(s) for exiting PSR. If multiple factors caused PSR to be exited, the driver should attempt to set all appropriate bit-field reasons. However, it is more important that flags should not be set if the reason was not the trigger to exit PSR, than it is to capture all the reasons which did trigger the exit. This is because once PSR has been exited, the driver should not subsequently report additional reasons that PSR would have been exited so under reporting is valid, as long as at least one reason is provided.

If the panel and driver support PSR2, where updates do not require a full frame to be sent to the panel in order to refresh a smaller portion, such updates should still be reported to the OS while exiting PSR. For example, if the display is in PSR and the cursor shape is changed without any other updates, the driver should be able to send a small fraction of the full frame of pixels, likely only the lines containing the cursor. In this case, the driver should still report that PSR has been exited, with reason *CursorUpdate*. In a later release, extra diagnostic fields may be added to distinguish partial and full updates.
