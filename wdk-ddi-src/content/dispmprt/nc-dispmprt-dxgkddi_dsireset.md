---
UID: NC:dispmprt.DXGKDDI_DSIRESET
title: DXGKDDI_DSIRESET
ms.date: 01/30/2020
ms.topic: language-reference
targetos: Windows
description: 
tech.root: display
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Next version of Windows 10
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
 - DXGKDDI_DSIRESET
f1_keywords:
 - dispmprt/DXGKDDI_DSIRESET
dev_langs:
 - c++
---

# DXGKDDI_DSIRESET callback function

## -description

## -parameters

### -param Context

[in] <!-- ????? -->

### -param TargetId

[in] Target identifier of the monitor.

### -param pArgs

[out] Pointer to a [DXGI_DSI_CAPS](ns-dispmprt-dxgk_dsi_caps.md) structure.

## -returns

*DxgkddiDsiReset* returns STATUS_SUCCESS if it succeeds; otherwise it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

If the OEM panel driver detects that the panel is in a bad state, it sends an [IOCTL_MIPI_DSI_RESET]() to request a reset of the device under graphics driver and OS control. A reset is necessarily a heavy-weight operation which will cause display blanking for multiple frames and therefore should only be used as a last resort.

Normal panel operation cannot be continued while processing a reset so the OS will treat it very similarly to a display mode change, flushing pending GPU activity, including any flips, and blocking new work until complete.  The OS translates the IOCTL into a *DxgkDsiReset* DDI call.  The driver should completely remove power from the panel and reinitialize it from scratch, and after the appropriate delay, perform any actions it needs to in order to restore the panel to a workable state before returning.  When set, the `SecondaryPort` flag indicates that the reset should be targeted to a secondary panel rather than the primary.

If the graphics driver requires a full mode set in order to perform or restore from a panel reset, it should set the output flag `NeedModeSet`.  If set upon return from the call, the OS will respond with a [*DxgkDdiSetTimingsFromVidPn*](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_settimingsfromvidpn) call before unblocking normal activity.  The driver may choose to defer some of the reset work to this call if needed, provided that a workable state is expected following the set timings call.

The graphics driver should report any low-level MIPI errors detected and not handled by the driver via the `MipiErrors` output field.

If an unrecoverable error occurs during the reset, the graphics driver should set the `ResetFailed` output flag. This is expected to be a catastrophic failure. The graphics driver should also signal that no display is available on the target by indicating that an unplug has occurred using the [*DxgkCbIndicateConnectorChange*](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_indicate_connector_change) callback and then responding to [*DxgkDdiQueryConnectionChange*](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryconnectionchange) by reporting a TargetStatusDisconnected for the target which has failed.

The output fields will be propagated back to the output buffer of the IOCTL.

## -see-also

[*DxgkCbIndicateConnectorChange*](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_indicate_connector_change)

[*DxgkDdiQueryConnectionChange*](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryconnectionchange)

[*DxgkDdiSetTimingsFromVidPn*](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_settimingsfromvidpn)

[IOCTL_MIPI_DSI_RESET]()