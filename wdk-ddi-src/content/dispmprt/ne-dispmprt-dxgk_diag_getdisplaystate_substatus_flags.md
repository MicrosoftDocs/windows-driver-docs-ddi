---
UID: NE:dispmprt._DXGK_DIAG_GETDISPLAYSTATE_SUBSTATUS_FLAGS
title: DXGK_DIAG_GETDISPLAYSTATE_SUBSTATUS_FLAGS
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: DXGK_DIAG_GETDISPLAYSTATE_SUBSTATUS_FLAGS specifies the substatus for per target diagnostic data collection.
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
 - _DXGK_DIAG_GETDISPLAYSTATE_SUBSTATUS_FLAGS
 - DXGK_DIAG_GETDISPLAYSTATE_SUBSTATUS_FLAGS
f1_keywords:
 - dispmprt/_DXGK_DIAG_GETDISPLAYSTATE_SUBSTATUS_FLAGS
 - dispmprt/DXGK_DIAG_GETDISPLAYSTATE_SUBSTATUS_FLAGS
dev_langs:
 - c++
---

# DXGK_DIAG_GETDISPLAYSTATE_SUBSTATUS_FLAGS enumeration

## -description

**DXGK_DIAG_GETDISPLAYSTATE_SUBSTATUS_FLAGS** specifies the substatus for per target diagnostic data collection.

## -enum-fields

### -field DXGK_DIAG_GETDISPLAYSTATE_SUCCESS

No errors occurred on the given vidpntarget while collecting the diagnostic information.

### -field DXGK_DIAG_GETDISPLAYSTATE_CAUSED_GLITCH

A user-visible glitch occurred on a given vidpntarget while collecting the diagnostic information.

### -field DXGK_DIAG_GETDISPLAYSTATE_CHANGED_DISPLAY_STATE

A display state change (hardware or software) was caused while collecting the diagnostic information on the given vidpntarget.

### -field DXGK_DIAG_GETDISPLAYSTATE_MONITOR_NOT_CONNECTED

No monitor was detected as connected on the given vidpntarget.

### -field DXGK_DIAG_GETDISPLAYSTATE_TIMEOUT

The driver hit a timeout while collecting the diagnostic information on a given vidpntarget.

### -field DXGK_DIAG_GETDISPLAYSTATE_ERROR_HARDWARE

The driver hit a hardware error while collecting the diagnostic information on a given vidpntarget.

### -field DXGK_DIAG_GETDISPLAYSTATE_ERROR_DRIVER

The driver hit a software error while collecting the diagnostic information on a given vidpntarget.

### -field DXGK_DIAG_GETDISPLAYSTATE_VIDPNTARGETID_NOT_FOUND

The driver did not find the VidPnTargetId provided by the OS in the DDI call.

## -remarks

The **DXGK_DIAG_GETDISPLAYSTATE_SUBSTATUS_FLAGS** enumeration is a member of the [**DXGK_DISPLAYSTATE_NONINTRUSIVE**](ns-dispmprt-dxgk_displaystate_nonintrusive.md) structure. It is used while gathering display diagnostic information via calls to [**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md).

In rare cases where a platform-specific implementation requires the driver to carry out intrusive operations during a call to **DxgkDdiGetDisplayStateNonIntrusive**, the driver should carry out these operations but must set **DXGK_DIAG_GETDISPLAYSTATE_SUBSTATUS_FLAGS** to DXGK_DIAG_GETDISPLAYSTATE_CAUSED_GLITCH or DXGK_DIAG_GETDISPLAYSTATE_CHANGED_DISPLAY_STATE accordingly. The OS can use this information to decide whether to call the DDI for error scenarios only on a given system.

The substatus information helps the driver succeed the overall [**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md) call even if there were failure or errors on some of the targets.

## -see-also

[**DXGK_DISPLAYSTATE_NONINTRUSIVE**](ns-dispmprt-dxgk_displaystate_nonintrusive.md)

[**DXGKARG_GETDISPLAYSTATENONINTRUSIVE**](ns-dispmprt-dxgkarg_getdisplaystatenonintrusive.md)

[**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md)
