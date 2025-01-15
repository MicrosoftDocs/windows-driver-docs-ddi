---
UID: NC:dispmprt.DXGKDDI_DISPLAYMUX_PRE_SWITCH_TO
tech.root: display
title: DXGKDDI_DISPLAYMUX_PRE_SWITCH_TO
ms.date: 01/13/2025
targetos: Windows
description: Learn more about the DXGKDDI_DISPLAYMUX_PRE_SWITCH_TO function.
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
 - DXGKDDI_DISPLAYMUX_PRE_SWITCH_TO
f1_keywords:
 - DXGKDDI_DISPLAYMUX_PRE_SWITCH_TO
 - dispmprt/DXGKDDI_DISPLAYMUX_PRE_SWITCH_TO
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_DISPLAYMUX_PRE_SWITCH_TO
---

## -description

*Dxgkrnl* calls the kernel-mode display driver's (KMD) **DxgkddiDisplayMuxPreSwitchTo** function to notify the driver currently not connected to the display that the display is about to be switched to its GPU.

## -parameters

### -param DriverContext

[in] Handle to a context block that is associated with a display adapter. KMD's [**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md) function previously provided this handle to *Dxgkrnl*.

### -param VidPnTargetId

[in] The VidPN target that the DDI is being called for.

### -param CurrentBrightnessLevel

[in] The current brightness level for the panel.

## -returns

**DxgkddiDisplayMuxPreSwitchTo** returns STATUS_SUCCESS if it succeeds. Otherwise, it returns an appropriate NT_STATUS error code.

## -remarks

This DDI is called under [synchronization level 2](/windows-hardware/drivers/display/threading-and-synchronization-second-level).

For more information, see [Automatic Display Switch](/windows-hardware/drivers/display/automatic-display-switch).

## -see-also

[**DxgkddiDisplayMuxPreSwitchAway**](nc-dispmprt-dxgkddi_displaymux_pre_switch_away.md)
