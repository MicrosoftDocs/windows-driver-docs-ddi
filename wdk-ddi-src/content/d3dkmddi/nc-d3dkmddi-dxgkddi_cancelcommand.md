---
UID: NC:d3dkmddi.DXGKDDI_CANCELCOMMAND
title: DXGKDDI_CANCELCOMMAND (d3dkmddi.h)
description: Cleans up internal resources associated with a direct memory access (DMA) packet that was in the GPU scheduler's software queue but never reached the hardware queue because the device went into an error state.
old-location: display\dxgkddicancelcommand.htm
ms.date: 05/10/2018
keywords: ["DXGKDDI_CANCELCOMMAND callback function"]
ms.keywords: DXGKDDI_CANCELCOMMAND, DXGKDDI_CANCELCOMMAND callback, DxgkDdiCancelCommand, DxgkDdiCancelCommand callback function [Display Devices], d3dkmddi/DxgkDdiCancelCommand, display.dxgkddicancelcommand
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_CANCELCOMMAND
 - d3dkmddi/DXGKDDI_CANCELCOMMAND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DXGKDDI_CANCELCOMMAND
---

# DXGKDDI_CANCELCOMMAND callback function


## -description

Cleans up internal resources associated with a direct memory access (DMA) packet that was in the GPU scheduler's software queue but  never reached the hardware queue because the device went into an error state. Such an error state is typically caused by a <a href="/windows-hardware/drivers/display/timeout-detection-and-recovery">Timeout Detection and Recovery (TDR)</a> event.

## -parameters

### -param hAdapter

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.

### -param pCancelCommand

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_cancelcommand">DXGKARG_CANCELCOMMAND</a> structure that specifies resources to be cleaned up after a command is removed from the hardware  queue.

## -returns

Returns <b>STATUS_SUCCESS</b> upon successful completion. If the driver instead returns an error code, the operating system causes a system bugcheck to occur. For more information, see the following Remarks section.

## -remarks

<div class="alert"><b>Note</b>  The DirectX graphics kernel subsystem calls this function only if the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_vidschcaps">DXGK_VIDSCHCAPS</a>.<b>CancelCommandAware</b> member is set.</div>
<div> </div>
If the driver returns an error code, the DirectX graphics kernel subsystem  causes a system bugcheck to occur. In a crash dump file, the error is noted by the message <b>BugCheck 0x119</b>, which has the following four parameters.

<ol>
<li>0x9</li>
<li>The NTSTATUS error code returned from the failed driver call</li>
<li>A pointer to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_cancelcommand">DXGKARG_CANCELCOMMAND</a> structure</li>
<li>A pointer to an internal scheduler data structure</li>
</ol>

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_cancelcommand">DXGKARG_CANCELCOMMAND</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_vidschcaps">DXGK_VIDSCHCAPS</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>

