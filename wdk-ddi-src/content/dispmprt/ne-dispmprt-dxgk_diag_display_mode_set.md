---
UID: NE:dispmprt._DXGK_DIAG_DISPLAY_MODE_SET
title: DXGK_DIAG_DISPLAY_MODE_SET
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: DXGK_DIAG_DISPLAY_MODE_SET provides a driver's last mode set state to the operating system (OS) when it is gathering nonintrusive display diagnostic information.
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
 - _DXGK_DIAG_DISPLAY_MODE_SET
 - DXGK_DIAG_DISPLAY_MODE_SET
f1_keywords:
 - dispmprt/_DXGK_DIAG_DISPLAY_MODE_SET
 - dispmprt/DXGK_DIAG_DISPLAY_MODE_SET
dev_langs:
 - c++
---

# DXGK_DIAG_DISPLAY_MODE_SET enumeration

## -description

**DXGK_DIAG_DISPLAY_MODE_SET** provides a driver's last mode set state to the operating system (OS) when it is gathering nonintrusive display diagnostic information.

## -enum-fields

### -field DXGK_DIAG_DISPLAY_MODE_SET_UNINITIALIZED

Reserved for OS use during diagnostic initialization.

### -field DXGK_DIAG_DISPLAY_MODE_SET_NO

The driver did not complete the last mode set successfully.

### -field DXGK_DIAG_DISPLAY_MODE_SET_YES

The driver completed the last mode set successfully.

## -remarks

The **DXGK_DIAG_DISPLAY_MODE_SET** enumeration is a member of the [**DXGK_DISPLAYSTATE_NONINTRUSIVE**](ns-dispmprt-dxgk_displaystate_nonintrusive.md) structure. It is used while gathering display diagnostic information via calls to [**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md).

While the OS tracks whether the last Set mode call succeeded, **DXGK_DIAG_DISPLAY_MODE_SET** provides the driver's state regarding mode set on a given target to compare against the OS state. For the OS, a mode set operation mainly consists of a SetTimings DDI call. However, for drivers, a mode set usually means multiple internal operations to set the hardware timings correctly. The OS can use **DXGK_DIAG_DISPLAY_MODE_SET** to determine the overall driver state for mode set and if it is considered successful.

## -see-also

[**DXGK_DISPLAYSTATE_NONINTRUSIVE**](ns-dispmprt-dxgk_displaystate_nonintrusive.md)

[**DXGKARG_GETDISPLAYSTATENONINTRUSIVE**](ns-dispmprt-dxgkarg_getdisplaystatenonintrusive.md)

[**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md)
