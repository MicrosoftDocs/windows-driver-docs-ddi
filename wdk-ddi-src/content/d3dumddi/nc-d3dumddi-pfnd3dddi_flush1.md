---
UID: NC:d3dumddi.PFND3DDDI_FLUSH1
title: PFND3DDDI_FLUSH1 (d3dumddi.h)
description: Called by the Microsoft Direct3D runtime to submit outstanding hardware commands that are in the hardware command buffer to the display miniport driver. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\pfnflush1.htm
tech.root: display
ms.assetid: 6BAC104A-85CE-42FC-AE30-969B2FF6AFEF
ms.date: 05/10/2018
keywords: ["PFND3DDDI_FLUSH1 callback function"]
ms.keywords: PFND3DDDI_FLUSH1, PFND3DDDI_FLUSH1 callback, d3dumddi/pfnFlush1, display.pfnflush1, pfnFlush1, pfnFlush1 callback function [Display Devices]
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - "d3dumddi/pfnFlush1"
 - "pfnFlush1"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dumddi.h
api_name:
 - pfnFlush1
product:
 - Windows
---

# PFND3DDDI_FLUSH1 callback function

## -description

Called by the Microsoft Direct3D runtime to submit outstanding hardware commands that are in the hardware command buffer to the display miniport driver. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param FlushFlags

A value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-d3dddi_flush_flags">D3DDDI_FLUSH_FLAGS</a> enumeration that indicates whether the driver should continue to submit command buffers if there have been no new commands.

## -returns

If this routine succeeds, it returns <b>S_OK</b>. Otherwise, it returns an <b>HRESULT</b> error code.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-d3dddi_flush_flags">D3DDDI_FLUSH_FLAGS</a>

