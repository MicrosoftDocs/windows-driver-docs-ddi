---
UID: NS:dispmprt._DXGKARG_DISPLAYSTATE_INTRUSIVE
title: DXGK_DISPLAYSTATE_INTRUSIVE
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: The **DXGK_DISPLAYSTATE_INTRUSIVE** structure holds display state during diagnostic data collection.
tech.root: display
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_DISPLAYSTATE_INTRUSIVE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKARG_DISPLAYSTATE_INTRUSIVE
 - DXGK_DISPLAYSTATE_INTRUSIVE
f1_keywords:
 - dispmprt/_DXGKARG_DISPLAYSTATE_INTRUSIVE
 - dispmprt//DXGK_DISPLAYSTATE_INTRUSIVE
 - DXGK_DISPLAYSTATE_INTRUSIVE
dev_langs:
 - c++
---

# DXGK_DISPLAYSTATE_INTRUSIVE structure

## -description

The **DXGK_DISPLAYSTATE_INTRUSIVE** structure holds display state during diagnostic data collection.

## -struct-fields

### -field VidPnTargetId

[in] Integer value that identifies a particular video present source.

### -field MonitorState

A [**DXGK_DIAG_MONITOR_STATE**](ne-dispmprt-dxgk_diag_monitor_state.md) value.

### -field DisplayScanoutState

A [**DXGK_DIAG_DISPLAY_SCANOUT_STATE**](ne-dispmprt-dxgk_diag_display_scanout_state.md) value.

### -field DisplaySampledGamma

A [**DXGK_DIAG_DISPLAY_SAMPLED_GAMMA**](ne-dispmprt-dxgk_diag_display_sampled_gamma.md) value.

### -field DisplayBufferContent

A [**DXGK_DIAG_SCANOUT_BUFFER_CONTENT**](ne-dispmprt-dxgk_diag_scanout_buffer_content.md) value.

### -field DisplayErrorState

A [**DXGK_DIAG_DISPLAY_HARDWARE_ERROR_STATE**](ne-dispmprt-dxgk_diag_display_hardware_error_state.md) value.

### -field DisplayBandwidth

A [**DXGK_DIAG_DISPLAY_HARDWARE_BANDWIDTH**](ne-dispmprt-dxgk_diag_display_hardware_bandwidth.md) value.

### -field ReturnSubStatus

A [**DXGK_DIAG_GETDISPLAYSTATE_SUBSTATUS_FLAGS**](ne-dispmprt-dxgk_diag_getdisplaystate_substatus_flags.md) value.

## -remarks

A pointer to an array of pointers to **DXGK_DISPLAYSTATE_INTRUSIVE** structures is contained in the [**DXGKARG_GETDISPLAYSTATEINTRUSIVE**](ns-dispmprt-dxgkarggetdisplaystatenonintrusive.md) structure, which is passed in calls to [**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md) during diagnostic data collection.

## -see-also

[**DXGK_DIAG_DISPLAY_HARDWARE_BANDWIDTH**](ne-dispmprt-dxgk_diag_display_hardware_bandwidth.md)

[**DXGK_DIAG_DISPLAY_HARDWARE_ERROR_STATE**](ne-dispmprt-dxgk_diag_display_hardware_error_state.md)

[**DXGK_DIAG_DISPLAY_SAMPLED_GAMMA**](ne-dispmprt-dxgk_diag_display_sampled_gamma.md)

[**DXGK_DIAG_DISPLAY_SCANOUT_STATE**](ne-dispmprt-dxgk_diag_display_scanout_state.md)

[**DXGK_DIAG_GETDISPLAYSTATE_SUBSTATUS_FLAGS**](ne-dispmprt-dxgk_diag_getdisplaystate_substatus_flags.md)

[**DXGK_DIAG_MONITOR_STATE**](ne-dispmprt-dxgk_diag_monitor_state.md)

[**DXGK_DIAG_SCANOUT_BUFFER_CONTENT**](ne-dispmprt-dxgk_diag_scanout_buffer_content.md)

[**DXGKARG_GETDISPLAYSTATEINTRUSIVE**](ns-dispmprt-dxgkarg_getdisplaystatenonintrusive.md)

[**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md)
