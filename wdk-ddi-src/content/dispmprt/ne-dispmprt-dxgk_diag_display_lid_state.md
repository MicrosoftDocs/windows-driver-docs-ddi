---
UID: NE:dispmprt._DXGK_DIAG_DISPLAY_LID_STATE
title: DXGK_DIAG_DISPLAY_LID_STATE
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: DXGK_DIAG_DISPLAY_LID_STATE provides the lid state of the target to the operating system (OS) when it is gathering nonintrusive display diagnostic information.
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
 - _DXGK_DIAG_DISPLAY_LID_STATE
 - DXGK_DIAG_DISPLAY_LID_STATE
f1_keywords:
 - _DXGK_DIAG_DISPLAY_LID_STATE
 - dispmprt/_DXGK_DIAG_DISPLAY_LID_STATE
 - DXGK_DIAG_DISPLAY_LID_STATE
 - dispmprt/DXGK_DIAG_DISPLAY_LID_STATE
dev_langs:
 - c++
---

# DXGK_DIAG_DISPLAY_LID_STATE enumeration


## -description

**DXGK_DIAG_DISPLAY_LID_STATE** provides the lid state of the target to the operating system (OS) when it is gathering nonintrusive display diagnostic information.

## -enum-fields

### -field DXGK_DIAG_DISPLAY_LID_STATE_UNINITIALIZED

Reserved for OS use during diagnostic initialization.

### -field DXGK_DIAG_DISPLAY_LID_STATE_NOTAPPLICABLE

Lid state is not applicable on this target. This would be the value used for most of the targets which are not internal displays.

### -field DXGK_DIAG_DISPLAY_LID_STATE_OPEN

The lid of the display is currently open, according to driver state.

### -field DXGK_DIAG_DISPLAY_LID_STATE_CLOSE

The lid of the display is currently closed, according to driver state.

### -field DXGK_DIAG_DISPLAY_LID_STATE_UNKNOWN

The driver does not know the current lid state. A driver should only use this value when it doesn't maintain/cache lid state internally.

## -remarks

The **DXGK_DIAG_DISPLAY_LID_STATE** enumeration is a member of the [**DXGK_DISPLAYSTATE_NONINTRUSIVE**](ns-dispmprt-dxgk_displaystate_nonintrusive.md) structure. It is used while gathering display diagnostic information via calls to [**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md).

**DXGK_DIAG_DISPLAY_LID_STATE** is only applicable to form factors which have a lid. If the driver caches the current state of the lid (open or close) then we want to compare it against to OS state.

## -see-also

[**DXGK_DISPLAYSTATE_NONINTRUSIVE**](ns-dispmprt-dxgk_displaystate_nonintrusive.md)

[**DXGKARG_GETDISPLAYSTATENONINTRUSIVE**](ns-dispmprt-dxgkarg_getdisplaystatenonintrusive.md)

[**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md)

