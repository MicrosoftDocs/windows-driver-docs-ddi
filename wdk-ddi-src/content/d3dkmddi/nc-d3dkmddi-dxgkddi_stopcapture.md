---
UID: NC:d3dkmddi.DXGKDDI_STOPCAPTURE
title: DXGKDDI_STOPCAPTURE (d3dkmddi.h)
description: The DxgkDdiStopCapture function stops the capture hardware from using the given allocation as a capture buffer.
old-location: display\dxgkddistopcapture.htm
ms.assetid: e5d622cc-c550-44cf-8923-5092226066d9
ms.date: 05/10/2018
keywords: ["DXGKDDI_STOPCAPTURE callback function"]
ms.keywords: DXGKDDI_STOPCAPTURE, DXGKDDI_STOPCAPTURE callback, DmFunctions_108ab359-fe5b-46f2-bc1b-f1f91bd5b327.xml, DxgkDdiStopCapture, DxgkDdiStopCapture callback function [Display Devices], d3dkmddi/DxgkDdiStopCapture, display.dxgkddistopcapture
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
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
 - "d3dkmddi/DxgkDdiStopCapture"
 - "DxgkDdiStopCapture"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiStopCapture
product:
 - Windows
---

# DXGKDDI_STOPCAPTURE callback function

## -description

The <i>DxgkDdiStopCapture</i> function stops the capture hardware from using the given allocation as a capture buffer.

## -parameters

### -param hAdapter

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.

### -param pStopCapture

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_stopcapture">DXGKARG_STOPCAPTURE</a> structure that contains the handle to the allocation that is used as a capture buffer.

## -returns

<i>DxgkDdiStopCapture</i> returns STATUS_SUCCESS, or an appropriate error result if the allocation is not successfully stopped.

## -remarks

When a capture buffer is destroyed, the DirectX graphics kernel subsystem calls the <i>DxgkDdiStopCapture</i> function to inform the display miniport driver to stop the capture hardware from using the allocation as the capture buffer. If the capture hardware already stopped using the allocation, the driver should ignore the call.

<i>DxgkDdiStopCapture</i> should be made pageable.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_stopcapture">DXGKARG_STOPCAPTURE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>

