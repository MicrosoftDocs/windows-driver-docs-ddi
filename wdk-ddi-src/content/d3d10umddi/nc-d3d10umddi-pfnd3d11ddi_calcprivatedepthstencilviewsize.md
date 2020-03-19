---
UID: NC:d3d10umddi.PFND3D11DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE
title: PFND3D11DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE (d3d10umddi.h)
description: The CalcPrivateDepthStencilViewSize(D3D11) function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a depth-stencil view.
old-location: display\calcprivatedepthstencilviewsize_d3d11_.htm
ms.assetid: d92e3bde-9527-401e-aafd-4ba39603d4a7
ms.date: 05/10/2018
keywords: ["PFND3D11DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE callback function"]
ms.keywords: CalcPrivateDepthStencilViewSize, CalcPrivateDepthStencilViewSize callback function [Display Devices], PFND3D11DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE, PFND3D11DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE callback, UserModeDisplayDriverDx11_Functions_865f13d6-ea1c-4e9f-94b2-7f77d10c8283.xml, d3d10umddi/CalcPrivateDepthStencilViewSize, display.calcprivatedepthstencilviewsize_d3d11_
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcPrivateDepthStencilViewSize(D3D11) is supported beginning with the Windows 7 operating system.
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
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d10umddi/CalcPrivateDepthStencilViewSize"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CalcPrivateDepthStencilViewSize
product:
 - Windows
---

# PFND3D11DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE callback function

## -description

The <b>CalcPrivateDepthStencilViewSize(D3D11)</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a depth-stencil view.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateDepthStencilView* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createdepthstencilview">D3D11DDIARG_CREATEDEPTHSTENCILVIEW</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

<b>CalcPrivateDepthStencilViewSize(D3D11)</b> returns the size of the memory region that the driver requires to create a depth-stencil view.

## -remarks



## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createdepthstencilview">D3D11DDIARG_CREATEDEPTHSTENCILVIEW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>

