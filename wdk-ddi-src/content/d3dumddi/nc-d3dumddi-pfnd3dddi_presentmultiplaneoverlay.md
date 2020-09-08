---
UID: NC:d3dumddi.PFND3DDDI_PRESENTMULTIPLANEOVERLAY
title: PFND3DDDI_PRESENTMULTIPLANEOVERLAY (d3dumddi.h)
description: Called by the Microsoft Direct3D runtime to notify the user-mode display driver that an application finished rendering and requests that the driver display the source surface by either copying or flipping or that the driver perform a color-fill operation. Must be implemented by Windows Display Driver Model (WDDM) 1.3 or later drivers that support multiplane overlays.
old-location: display\pfnpresentmultiplaneoverlay__d3d_.htm
tech.root: display
ms.assetid: 3AC47977-A5F3-44A6-8F89-A1EA5E0BB6E4
ms.date: 05/10/2018
keywords: ["PFND3DDDI_PRESENTMULTIPLANEOVERLAY callback function"]
ms.keywords: PFND3DDDI_PRESENTMULTIPLANEOVERLAY, PFND3DDDI_PRESENTMULTIPLANEOVERLAY (D3D) callback, d3dumddi/pfnPresentMultiPlaneOverlay, display.pfnpresentmultiplaneoverlay__d3d_, pfnPresentMultiPlaneOverlay, pfnPresentMultiPlaneOverlay callback function [Display Devices]
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
 - PFND3DDDI_PRESENTMULTIPLANEOVERLAY
 - d3dumddi/PFND3DDDI_PRESENTMULTIPLANEOVERLAY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dumddi.h
api_name:
 - pfnPresentMultiPlaneOverlay
product:
 - Windows
---

# PFND3DDDI_PRESENTMULTIPLANEOVERLAY callback function


## -description

Called by the Microsoft Direct3D runtime to notify the user-mode display driver that an application finished rendering and requests that the driver display the source surface by either copying or flipping or that the driver perform a color-fill operation. Must be implemented by Windows Display Driver Model (WDDM) 1.3 or later drivers that support multiplane overlays.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pPresent* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddiarg_presentmultiplaneoverlay">D3DDDIARG_PRESENTMULTIPLANEOVERLAY</a> structure that describes how to display to the destination surface.

## -returns

If this routine succeeds, it returns <b>S_OK</b>. Otherwise, it returns an <b>HRESULT</b> error code.

## -remarks

When the user-mode display driver successfully completes its processing of a call to this function, it presents the source surface to the display by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_presentmultiplaneoverlaycb">pfnPresentMultiPlaneOverlayCb (D3D)</a> function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddiarg_presentmultiplaneoverlay">D3DDDIARG_PRESENTMULTIPLANEOVERLAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_presentmultiplaneoverlaycb">pfnPresentMultiPlaneOverlayCb (D3D)</a>

