---
UID: NS:dispmprt._DXGK_DISPLAYSTATE_NONINTRUSIVE
title: DXGK_DISPLAYSTATE_NONINTRUSIVE
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: The DXGK_DISPLAYSTATE_NONINTRUSIVE structure holds display state during nonintrusive diagnostic data collection.
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
req.typenames: DXGK_DISPLAYSTATE_NONINTRUSIVE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_DISPLAYSTATE_NONINTRUSIVE
 - DXGK_DISPLAYSTATE_NONINTRUSIVE
f1_keywords:
 - dispmprt/_DXGK_DISPLAYSTATE_NONINTRUSIVE
 - dispmprt//DXGK_DISPLAYSTATE_NONINTRUSIVE
 - DXGK_DISPLAYSTATE_NONINTRUSIVE
dev_langs:
 - c++
---

# DXGK_DISPLAYSTATE_NONINTRUSIVE structure

## -description

The **DXGK_DISPLAYSTATE_NONINTRUSIVE** structure holds display state during nonintrusive diagnostic data collection.

## -struct-fields

### -field VidPnTargetId

[in] Integer value that identifies a particular video present source.

### -field DisplayConnectivity

A [**DXGK_DIAG_DISPLAY_CONNECTIVITY**](ne-dispmprt-dxgk_diag_display_connectivity.md) value.

### -field DisplayLidState

A [**DXGK_DIAG_DISPLAY_LID_STATE**](ne-dispmprt-dxgk_diag_display_lid_state.md) value.

### -field DisplayTopology

A [**DXGK_DIAG_DISPLAY_TOPOLOGY**](ne-dispmprt-dxgk_diag_display_topology.md) value.

### -field DisplayLinkState

A [**DXGK_DIAG_DISPLAY_LINK_STATE**](ne-dispmprt-dxgk_diag_display_link_state.md) value.

### -field DisplayModeSet

A [**DXGK_DIAG_DISPLAY_MODE_SET**](ne-dispmprt-dxgk_diag_display_mode_set.md) value.

### -field ReturnSubStatus

A [**DXGK_DIAG_GETDISPLAYSTATE_SUBSTATUS_FLAGS**](ne-dispmprt-dxgk_diag_getdisplaystate_substatus_flags.md) value.

## -remarks

A pointer to an array of pointers to **DXGK_DISPLAYSTATE_NONINTRUSIVE** structures is contained in the [**DXGKARG_GETDISPLAYSTATENONINTRUSIVE**](ns-dispmprt-dxgkarggetdisplaystatenonintrusive.md) structure, which is passed in calls to [**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md) during nonintrusive diagnostic data collection.

## -see-also

[**DXGK_DIAG_DISPLAY_CONNECTIVITY**](ne-dispmprt-dxgk_diag_display_connectivity.md)

[**DXGK_DIAG_DISPLAY_LID_STATE**](ne-dispmprt-dxgk_diag_display_lid_state.md)

[**DXGK_DIAG_DISPLAY_LINK_STATE**](ne-dispmprt-dxgk_diag_display_link_state.md)

[**DXGK_DIAG_DISPLAY_MODE_SET**](ne-dispmprt-dxgk_diag_display_mode_set.md)

[**DXGK_DIAG_DISPLAY_TOPOLOGY**](ne-dispmprt-dxgk_diag_display_topology.md)

[**DXGKARG_GETDISPLAYSTATENONINTRUSIVE**](ns-dispmprt-dxgkarg_getdisplaystatenonintrusive.md)

[**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md)
