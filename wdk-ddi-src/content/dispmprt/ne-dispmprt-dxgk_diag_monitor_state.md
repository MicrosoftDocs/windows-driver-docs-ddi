---
UID: NE:dispmprt._DXGK_DIAG_MONITOR_STATE
title: DXGK_DIAG_MONITOR_STATE
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: DXGK_DIAG_MONITOR_STATE specifies the state of the monitors according to the miniport driver, indicating to the operating system (OS) whether the monitors are ready to receive the pixels.
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
 - _DXGK_DIAG_MONITOR_STATE
 - DXGK_DIAG_MONITOR_STATE
f1_keywords:
 - dispmprt/_DXGK_DIAG_MONITOR_STATE
 - dispmprt//DXGK_DIAG_MONITOR_STATE
 - DXGK_DIAG_MONITOR_STATE
dev_langs:
 - c++
---

# DXGK_DIAG_MONITOR_STATE enumeration

## -description

**DXGK_DIAG_MONITOR_STATE** specifies the state of the monitors according to the miniport driver, indicating to the operating system (OS) whether the monitors are ready to receive the pixels.

## -enum-fields

### -field DXGK_DIAG_MONITOR_STATE_UNINITIALIZED

Reserved for OS use during diagnostic initialization.

### -field DXGK_DIAG_MONITOR_READY

The monitor is initialized and setup, and is ready to receive pixels.

### -field DXGK_DIAG_MONITOR_NOT_READY

The monitor is not initialized or setup correctly, and is not ready to receive pixels.

### -field DXGK_DIAG_MONITOR_READY_NOTAPPLICABLE

The driver doesn't know the current state of the monitor. This value should be used only for monitors for which the driver has no insight into monitor state.

## -remarks

The **DXGK_DIAG_MONITOR_STATE** enumeration is a member of the [**DXGK_DISPLAYSTATE_INTRUSIVE**](ns-dispmprt-dxgk_displaystate_intrusive.md) structure. It is used while gathering display diagnostic information via calls to [**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md).

In many situations, the driver needs to initialize the monitor and set it up (typically by sending a command sequence) before it can start sending pixels to the monitor. Additionally, there might be some driver-initiated negotiation/handshaking done with the monitor before pixels can be sent. **DXGK_DIAG_MONITOR_STATE** specifies the final state of the monitors according to the miniport driver, indicating to the OS whether the monitors are ready to receive the pixels.

> [!NOTE]
> In some cases (like DisplayPort), **DXGK_DIAG_MONITOR_STATE** might overlap with [**DXGK_DIAG_DISPLAY_LINK_STATE**](ne-dispmprt-dxgk_diag_display_link_state). The purpose of this enumeration is to get the overall current status of the monitor irrespective of the bus/link state.

## -see-also

[**DXGK_DIAG_DISPLAY_LINK_STATE**](ne-dispmprt-dxgk_diag_display_link_state)

[**DXGK_DISPLAYSTATE_INTRUSIVE**](ns-dispmprt-dxgk_displaystate_intrusive.md)

[**DXGKARG_GETDISPLAYSTATEINTRUSIVE**](ns-dispmprt-dxgkarg_getdisplaystateintrusive.md)

[**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md)
