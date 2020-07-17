---
UID: NC:d3dkmddi.DXGKDDI_GETSCANLINE
title: DXGKDDI_GETSCANLINE (d3dkmddi.h)
description: The DxgkDdiGetScanLine function determines whether the specified video present target of a video present network (VidPN) is in vertical blanking mode and retrieves the current scan line.
old-location: display\dxgkddigetscanline.htm
ms.assetid: e37bb3c6-a0b6-409f-8a82-20ec7a931c6a
ms.date: 05/10/2018
keywords: ["DXGKDDI_GETSCANLINE callback function"]
ms.keywords: DXGKDDI_GETSCANLINE, DXGKDDI_GETSCANLINE callback, DmFunctions_135e90a4-1b44-4cd6-92fe-626dd389af9b.xml, DxgkDdiGetScanLine, DxgkDdiGetScanLine callback function [Display Devices], d3dkmddi/DxgkDdiGetScanLine, display.dxgkddigetscanline
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
 - "d3dkmddi/DxgkDdiGetScanLine"
 - "DxgkDdiGetScanLine"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiGetScanLine
product:
 - Windows
---

# DXGKDDI_GETSCANLINE callback function

## -description

The <i>DxgkDdiGetScanLine</i> function determines whether the specified video present target of a video present network (VidPN) is in vertical blanking mode and retrieves the current scan line.

## -parameters

### -param hAdapter

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.

### -param pGetScanLine

[in/out] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_getscanline">DXGKARG_GETSCANLINE</a> structure that contains the vertical blanking status of a video present target.

## -returns

<i>DxgkDdiGetScanLine</i> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.

## -remarks

<i>DxgkDdiGetScanLine</i> should be made pageable.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_getscanline">DXGKARG_GETSCANLINE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>

