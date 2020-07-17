---
UID: NE:dispmprt._DXGK_DIAG_DISPLAY_HARDWARE_ERROR_STATE
title: DXGK_DIAG_DISPLAY_HARDWARE_ERROR_STATE
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: The DXGK_DIAG_DISPLAY_HARDWARE_ERROR_STATE enum provides hardware error state information during diagnostic data collection.
tech.root: display
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dispmprt.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_DIAG_DISPLAY_HARDWARE_ERROR_STATE
 - DXGK_DIAG_DISPLAY_HARDWARE_ERROR_STATE
f1_keywords:
 - dispmprt/_DXGK_DIAG_DISPLAY_HARDWARE_ERROR_STATE
 - dispmprt/DXGK_DIAG_DISPLAY_HARDWARE_ERROR_STATE
 - ""
dev_langs:
 - c++
---

# DXGK_DIAG_DISPLAY_HARDWARE_ERROR_STATE enumeration

## -description

The **DXGK_DIAG_DISPLAY_HARDWARE_ERROR_STATE** enum provides hardware error state information during diagnostic data collection.

## -enum-fields

### -field DXGK_DIAG_DISPLAY_HARDWARE_ERROR_STATE_UNINITIALIZED

Reserved for OS use during diagnostic initialization.

### -field DXGK_DIAG_DISPLAY_HARDWARE_ERROR_NONE

No display pipeline hardware error state was detected.

### -field DXGK_DIAG_DISPLAY_HARDWARE_ERROR_SCANOUT_UNDERFLOW

The display scan out pipeline is hitting underflows during scan out of the current frame.

### -field DXGK_DIAG_DISPLAY_HARDWARE_ERROR_TDRNORECOVERY

The display pipeline could not recover after a TDR.

### -field DXGK_DIAG_DISPLAY_HARDWARE_ERROR_UNSPECIFIED

The display hardware is in an error state that doesn't fall under any of the above categories.

## -remarks

The **DXGK_DIAG_DISPLAY_HARDWARE_ERROR_STATE** enumeration is a member of the [**DXGK_DISPLAYSTATE_INTRUSIVE**](ns-dispmprt-dxgk_displaystate_intrusive.md) structure. It is used while gathering display diagnostic information via calls to [**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md).

**DXGK_DIAG_DISPLAY_HARDWARE_ERROR_STATE** informs the operating system whether the display hardware is in some kind of error state that might be causing issues with scan out or other display operations. For example, some black screens are caused right after the user hits TDRs. In such a situation, it is important that drivers notify the OS if after hitting TDR the display scan out pipeline hasn't recovered and there is no scan out going on.

## -see-also

[**DXGK_DISPLAYSTATE_INTRUSIVE**](ns-dispmprt-dxgk_displaystate_intrusive.md)

[**DXGKARG_GETDISPLAYSTATEINTRUSIVE**](ns-dispmprt-dxgkarg_getdisplaystateintrusive.md)

[**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md)
