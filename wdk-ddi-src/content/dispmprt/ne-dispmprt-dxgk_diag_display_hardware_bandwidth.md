---
UID: NE:dispmprt._DXGK_DIAG_DISPLAY_HARDWARE_BANDWIDTH
title: DXGK_DIAG_DISPLAY_HARDWARE_BANDWIDTH
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: The DXGK_DIAG_DISPLAY_HARDWARE_BANDWIDTH enum provides hardware bandwidth information during diagnostic data collection.
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
 - _DXGK_DIAG_DISPLAY_HARDWARE_BANDWIDTH
 - DXGK_DIAG_DISPLAY_HARDWARE_BANDWIDTH
f1_keywords:
 - dispmprt/_DXGK_DIAG_DISPLAY_HARDWARE_BANDWIDTH
 - dispmprt/DXGK_DIAG_DISPLAY_HARDWARE_BANDWIDTH
dev_langs:
 - c++
---

# DXGK_DIAG_DISPLAY_HARDWARE_BANDWIDTH enumeration

The **DXGK_DIAG_DISPLAY_HARDWARE_BANDWIDTH** enum provides hardware bandwidth information during diagnostic data collection.

## -description

## -enum-fields

### -field DXGK_DIAG_DISPLAY_HARDWARE_BANDWIDTH_UNINITIALIZED

Reserved for OS use during diagnostic initialization.

### -field DXGK_DIAG_DISPLAY_HARDWARE_BANDWIDTH_SUFFICIENT

The bandwidth required to drive the last set display mode on the given target is within the range of what the display hardware and monitor/link can support.

### -field DXGK_DIAG_DISPLAY_HARDWARE_LINK_BANDWIDTH_LIMITED

The bandwidth limitation is on the link or monitor end, and the link negotiation did not result in sufficient bandwidth. Do not set this field if the current target/monitor bus protocol cannot determine the bandwidth it supports.

### -field DXGK_DIAG_DISPLAY_HARDWARE_SOC_BANDWIDTH_LIMITED

The bandwidth limitation is on the display hardware side and silicon cannot support the currently needed bandwidth.

### -field DXGK_DIAG_DISPLAY_HARDWARE_BANDWIDTH_ERROR

This value should be used in rare cases where the driver has hit some error while doing any bandwidth calculations so that all other fields are still filled.

### -field DXGK_DIAG_DISPLAY_HARDWARE_BANDWIDTH_UNKNOWN

The driver could not calculate the bandwidth requirements for the given monitor/link and/or SOC. This value should be used in rare cases where the driver does not implement the calculation of bandwidth requirements.

## -remarks

The **DXGK_DIAG_DISPLAY_HARDWARE_BANDWIDTH** enumeration is a member of the [**DXGK_DISPLAYSTATE_INTRUSIVE**](ns-dispmprt-dxgk_displaystate_intrusive.md) structure. It is used while gathering display diagnostic information via calls to [**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md).

DXGK_DIAG_DISPLAY_HARDWARE_BANDWIDTH tells the operating system whether the display hardware including the link (for example, displayport) has sufficient bandwidth to drive the display on the given target at the last set mode (resolution, refresh rate).

## -see-also

[**DXGK_DISPLAYSTATE_INTRUSIVE**](ns-dispmprt-dxgk_displaystate_intrusive.md)

[**DXGKARG_GETDISPLAYSTATEINTRUSIVE**](ns-dispmprt-dxgkarg_getdisplaystateintrusive.md)

[**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md)
