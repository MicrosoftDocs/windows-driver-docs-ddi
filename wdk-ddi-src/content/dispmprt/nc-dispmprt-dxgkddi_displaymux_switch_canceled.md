---
UID: NC:dispmprt.DXGKDDI_DISPLAYMUX_SWITCH_CANCELED
tech.root: display
title: DXGKDDI_DISPLAYMUX_SWITCH_CANCELED
ms.date: 01/13/2025
targetos: Windows
description: Learn more about the DXGKDDI_DISPLAYMUX_SWITCH_CANCELED function.
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
 - DXGKDDI_DISPLAYMUX_SWITCH_CANCELED
f1_keywords:
 - DXGKDDI_DISPLAYMUX_SWITCH_CANCELED
 - dispmprt/DXGKDDI_DISPLAYMUX_SWITCH_CANCELED
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_DISPLAYMUX_SWITCH_CANCELED
---

## -description

*Dxgkrnl* calls the kernel-mode display driver's (KMD) **DxgkddiDisplayMuxSwitchCanceled** function to notify the driver that the switch sequence was canceled before being completed.

## -parameters

### -param DriverContext

[in] Handle to a context block that is associated with a display adapter. KMD's [**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md) function previously provided this handle to *Dxgkrnl*.

### -param VidPnTargetId

[in] The VidPN target that the DDI is being called for.

### -param MuxSwitchedToTarget

[in] Boolean value that indicates whether the display mux is currently switched to connect the target identified by **VidPnTargetId** to the panel.

## -returns

**DxgkddiDisplayMuxSwitchCanceled** returns **STATUS_SUCCESS** if it succeeds. Otherwise, it returns an appropriate error code.

## -remarks

This DDI is called under [synchronization level 2](/windows-hardware/drivers/display/threading-and-synchronization-second-level).

In general, the driver should revert any hardware or internal driver state that was modified as part of the switch sequence. The following table shows some examples of what the driver should do, but it isn't an exhaustive list.

| MuxSwitchedToTarget | Mux was switched to GPU before switch | Mux was switched away from GPU before switch |
| --- | --- | --- |
| FALSE | Ensure that the driver has turned off power to the internal panel, disabled brightness levels, and stopped sending brightness levels to the mux. The driver/GPU is ready for the next switch sequence. | Nothing |
| TRUE  | If the driver already reported the lid as disconnected then add a new connection change packet to report the lid as connected again. The driver/GPU should be ready for the [**DxgkddiSettimingsfromvidpn**](../d3dkmddi/nc-d3dkmddi-dxgkddi_settimingsfromvidpn.md) call that will occur shortly. On the next **DxgkddiSettimingsfromvidpn** call, the driver needs to ensure PSR is disabled. | If the driver hasn't already reported the lid as connected then add a connection change packet to report the lid as connected. The driver/GPU should be ready for **DxgkddiSettimingsfromvidpn** call that will occur shortly. On the next **DxgkddiSettimingsfromvidpn** call, the driver needs to ensure PSR is disabled. |

For more information, see [Automatic Display Switch](/windows-hardware/drivers/display/automatic-display-switch).

## -see-also

[**DxgkddiSettimingsfromvidpn**](../d3dkmddi/nc-d3dkmddi-dxgkddi_settimingsfromvidpn.md)
