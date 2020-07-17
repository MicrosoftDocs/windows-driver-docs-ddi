---
UID: NE:dispmprt._DXGK_DIAG_DISPLAY_LINK_STATE
title: DXGK_DIAG_DISPLAY_LINK_STATE
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: DXGK_DIAG_DISPLAY_LINK_STATE provides the display link state of the target to the operating system (OS) when it is gathering nonintrusive display diagnostic information.
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
 - _DXGK_DIAG_DISPLAY_LINK_STATE
 - DXGK_DIAG_DISPLAY_LINK_STATE
f1_keywords:
 - dispmprt/_DXGK_DIAG_DISPLAY_LINK_STATE
 - dispmprt/DXGK_DIAG_DISPLAY_LINK_STATE
 - ""
dev_langs:
 - c++
---

# DXGK_DIAG_DISPLAY_LINK_STATE enumeration

## -description

**DXGK_DIAG_DISPLAY_LINK_STATE** provides the display link state of the target to the operating system (OS) when it is gathering nonintrusive display diagnostic information.

## -enum-fields

### -field DXGK_DIAG_DISPLAY_LINK_STATE_UNINITIALIZED

Reserved for OS use during diagnostic initialization.

### -field DXGK_DIAG_DISPLAY_LINK_STATE_NOTAPPLICABLE

A driver should return this value if the target is of a type where there is no concept of link or there is no negotiation/handshaking between display hardware and the monitor (for example, VGA targets). This value should never be used for a DisplayPort based target.

### -field DXGK_DIAG_DISPLAY_LINK_STATE_STABLE

A driver should return this value if the link is in a stable state, indicating that negotiation/handshaking has been completed and the link is ready to receive pixel data.

### -field DXGK_DIAG_DISPLAY_LINK_STATE_FAILED

A driver should return this value if the link is in a failed state after attempting to negotiate the bandwidth or any other parameters with a given sink, such as monitor, hub, dongle, etc.

### -field DXGK_DIAG_DISPLAY_LINK_STATE_CONTINUOUS_TRAINING

A driver should return this value if the link is currently being trained. It doesn't matter if this is the first or subsequent link training attempt since it is expected that when the OS calls this diagnostic [**DXGK_DISPLAYSTATE_NONINTRUSIVE**](ns-dispmprt-dxgk_displaystate_nonintrusive.md) DDI, training should already been completed in the ideal scenario. a short time frame and hence is not in a stable state.

### -field DXGK_DIAG_DISPLAY_LINK_STATE_CONTINUOUS_TRAINING_STABLE

A driver should return this value if the link is currently in a stable state but only after multiple training attempts. There are scenarios where even though the link seems currently stable it can actually go back to training anytime.

### -field DXGK_DIAG_DISPLAY_LINK_STATE_CONTINUOUS_TRAINING_FAILED

A driver should return this value if the link is currently in the failed state but only after multiple training attempts. The difference between this state and DXGK_DIAG_DISPLAY_LINK_STATE_FAILED is that this value indicates that the link is potentially troublesome and goes into training state often.

## -remarks

The **DXGK_DIAG_DISPLAY_LINK_STATE** enumeration is a member of the [**DXGK_DISPLAYSTATE_NONINTRUSIVE**](ns-dispmprt-dxgk_displaystate_nonintrusive.md) structure. It is used while gathering display diagnostic information via calls to [**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md).

**DXGK_DIAG_DISPLAY_LINK_STATE** is not DisplayPort-specific. The link state refers to the state of any negotiation/handshaking between display hardware and the monitor before starting to send pixel data.

## -see-also

[**DXGK_DISPLAYSTATE_NONINTRUSIVE**](ns-dispmprt-dxgk_displaystate_nonintrusive.md)

[**DXGKARG_GETDISPLAYSTATENONINTRUSIVE**](ns-dispmprt-dxgkarg_getdisplaystatenonintrusive.md)

[**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md)
