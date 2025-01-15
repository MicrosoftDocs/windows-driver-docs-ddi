---
UID: NC:dispmprt.DXGKDDI_DISPLAYMUX_POST_SWITCH_TO_PHASE2
tech.root: display
title: DXGKDDI_DISPLAYMUX_POST_SWITCH_TO_PHASE2
ms.date: 01/13/2025
targetos: Windows
description: Learn more about the DXGKDDI_DISPLAYMUX_POST_SWITCH_TO_PHASE2 function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2, update 2025.01
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_DISPLAYMUX_POST_SWITCH_TO_PHASE2
f1_keywords:
 - DXGKDDI_DISPLAYMUX_POST_SWITCH_TO_PHASE2
 - dispmprt/DXGKDDI_DISPLAYMUX_POST_SWITCH_TO_PHASE2
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_DISPLAYMUX_POST_SWITCH_TO_PHASE2
---

## -description

*Dxgkrnl* calls the kernel-mode display driver's (KMD) **DxgkddiDisplayMuxPostSwitchToPhase2** function to notify the driver that the mux switch has completed, and that the driver is now connected to the display and should perform phase 2 tasks.

## -parameters

### -param DriverContext

[in] Handle to a context block that is associated with a display adapter. KMD's [**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md) function previously provided this handle to *Dxgkrnl*.

### -param VidPnTargetId

[in] The VidPN target that the DDI is being called for.

### -param pWasPanelInPSR

[out] Pointer to a Boolean value that the driver should set to indicate whether the panel was in panel self-refresh (PSR) when the driver took over control.

KMD should set this value to TRUE if the panel was in PSR. If the driver can't reliably determine whether the panel was in PSR, it should still set this value to TRUE. KMD should only return FALSE if it can reliably determine that the panel was not in PSR.

## -returns

**DxgkddiDisplayMuxPostSwitchToPhase2** returns STATUS_SUCCESS if it succeeds. Otherwise, it returns an appropriate error code.

## -remarks

This DDI is called under [synchronization level 2](/windows-hardware/drivers/display/threading-and-synchronization-second-level).

For more information, see [Automatic Display Switch](/windows-hardware/drivers/display/automatic-display-switch).

## -see-also

[**DxgkddiDisplayMuxPostSwitchToPhase1**](nc-dispmprt-dxgkddi_displaymux_post_switch_to_phase1.md)
