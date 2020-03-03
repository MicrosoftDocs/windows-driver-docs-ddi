---
UID: NE:dispmprt._DXGK_DIAG_DISPLAY_CONNECTIVITY
title: DXGK_DIAG_DISPLAY_CONNECTIVITY
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: DXGK_DIAG_DISPLAY_CONNECTIVITY provides the last status of the target to the operating system (OS) when it is gathering nonintrusive display diagnostic information.
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
 - _DXGK_DIAG_DISPLAY_CONNECTIVITY
 - DXGK_DIAG_DISPLAY_CONNECTIVITY
f1_keywords:
 - dispmprt/_DXGK_DIAG_DISPLAY_CONNECTIVITY
 - dispmprt/DXGK_DIAG_DISPLAY_CONNECTIVITY
dev_langs:
 - c++
---

# DXGK_DIAG_DISPLAY_CONNECTIVITY enumeration

## -description

**DXGK_DIAG_DISPLAY_CONNECTIVITY** provides the last status of the target to the operating system (OS) when it is gathering nonintrusive display diagnostic information.

## -enum-fields

### -field DXGK_DIAG_DISPLAY_CONNECTIVITY_UNINITIALIZED

Reserved for OS use during diagnostic initialization.

### -field DXGK_DIAG_DISPLAY_NOT_CONNECTED

No monitor is connected on the given target.

### -field DXGK_DIAG_DISPLAY_CONNECTED

A monitor is connected on the given target.

## -remarks

The **DXGK_DIAG_BASIC_DISPLAY_TOPOLOGY** enumeration is a member of the [**DXGK_DISPLAYSTATE_NONINTRUSIVE**](ns-dispmprt-dxgk_displaystate_nonintrusive.md) structure. It is used while gathering display diagnostic information via calls to [**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md).

A driver should return the last status (preferably the hardware status of whether the monitor is connected) and should not perform active detection. Active detection might change the state of display connectivity, which would trigger an OS path for handling a new display arrival during this diagnostic DDI. Note that the OS requests the driver for active detection when it is performing the recovery steps for black screens.

## -see-also

[**DXGK_DISPLAYSTATE_NONINTRUSIVE**](ns-dispmprt-dxgk_displaystate_nonintrusive.md)

[**DXGKARG_GETDISPLAYSTATENONINTRUSIVE**](ns-dispmprt-dxgkarg_getdisplaystatenonintrusive.md)

[**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md)
