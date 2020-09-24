---
UID: NI:ntddvdeo.IOCTL_MIPI_DSI_RESET
title: IOCTL_MIPI_DSI_RESET
description: IOCTL_MIPI_DSI_RESET requests the reset of a device under graphics driver and OS control.
tech.root: display
ms.assetid: 9c495955-2fbf-400d-9c75-379f64025993
ms.date: 03/24/2020
ms.topic: ioctl
req.header: ntddvdeo.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.max-support: 
targetos: Windows
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddvdeo.h
api_name:
 - IOCTL_MIPI_DSI_RESET
product:
 - Windows
f1_keywords:
 - IOCTL_MIPI_DSI_RESET
 - ntddvdeo/IOCTL_MIPI_DSI_RESET
---

# IOCTL_MIPI_DSI_RESET IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)


## -description

**IOCTL_MIPI_DSI_RESET** requests the reset of a device under graphics driver and OS control.

## -ioctlparameters

### -input-buffer

n/a

### -input-buffer-length

n/a

### -output-buffer

n/a

### -output-buffer-length

n/a

### -in-out-buffer

A [**DXGK_DSI_RESET**](../dispmprt/ns-dispmprt-dxgk_dsi_rset.md) structure.

### -inout-buffer-length

At least ```sizeof(DXGK_DSI_RESET)```

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code.

For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Mobile Industry Processor Interface (MIPI) Digital Serial Interface(DSI) IOCTLs must be handled by the monitor, oem-panel, or port/miniport driver.

If an OEM panel driver detects that the panel is in a bad state, it should send **IOCTL_MIPI_DSI_RESET** to request a reset of the device under graphics driver and OS control. The OS will coordinate the reset with the graphics driver. A reset is a heavy-weight operation that will cause display blanking for multiple frames, and should therefore be used only as a last resort.

Normal panel operation cannot continue while processing a reset, so the OS will treat is similarly to a display mode change, flushing pending GPU activity, including any flips, and blocking new work until complete. The OS translates the IOCTL into a [**DsiReset**](../dispmprt/nc-dispmprt_dxgk_dsireset.md) DDI call. The driver should completely remove power from the panel and reinitialize it from scratch, and after the appropriate delay, perform any actions it needs to in order to restore the panel to a workable state before returning. When set, the **SecondaryPort** flag indicates that the reset should be targeted to a secondary panel rather than the primary.

If the graphics driver requires a full mode set in order to perform or restore from a panel reset, it should set the output flag **NeedModeSet**. If set upon return from the call, the OS will respond with a [**DxgkDdiSetTimingsFromVidPn**](../d3dkmddi/nc-d3dkmddi-dxgkddi_settimingsfromvidpn.md) call before unblocking normal activity. The driver may chose to defer some of the reset work to this call if needed, provided that a workable state is expected following the set timings call.

The graphics driver should report any low-level MIPI errors detected and not handled by the driver via the **MipiErrors** output field.

If an unrecoverable error occurs during the reset, the graphics driver should set the **ResetFailed** output flag. This is expected to be a catastrophic failure. The graphics driver should also signal that no display is available on the target by indicating that an unplug has occurred using the [**DxgkCbIndicateConnectorChange**](../d3dkmddi/nc-d3dkmddi-dxgkcb_indicate_connector_change.md) callback and then responding to [**DxgkDdiQueryConnectionChange**](../d3dkmddi/nc-d3dkmddi-dxgkddi_queryconnectionchange.md) by reporting a **TargetStatusDisconnected** for the target which has failed.

The output fields will be propagated back to the output buffer of the IOCTL.

## -see-also

[**DsiReset**](../dispmprt/nc-dispmprt_dxgk_dsireset.md)

[**DXGK_DSI_RESET**](../dispmprt/ns-dispmprt-dxgk_dsi_reset.md)

[**IOCTL_MIPI_DSI_QUERY_CAPS**](ni-ntddvdeo-ioctl_mipi_dsi_query_caps.md)

[**IOCTL_MIPI_DSI_TRANSMISSION**](ni-ntddvdeo-ioctl_mipi_dsi_transmission.md)