---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE
title: PFND3D10DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE (d3d10umddi.h)
description: The CalcPrivateDepthStencilStateSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a depth stencil state.
old-location: display\calcprivatedepthstencilstatesize.htm
ms.assetid: dcc02e1e-97e0-4ccd-8329-8219cad5d09a
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE callback function"]
ms.keywords: CalcPrivateDepthStencilStateSize, CalcPrivateDepthStencilStateSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE, PFND3D10DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE callback, UserModeDisplayDriverDx10_Functions_9eb00c77-fbc0-443d-848b-b7e254de4efe.xml, d3d10umddi/CalcPrivateDepthStencilStateSize, display.calcprivatedepthstencilstatesize
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d10umddi/CalcPrivateDepthStencilStateSize"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CalcPrivateDepthStencilStateSize
product:
 - Windows
---

# PFND3D10DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE callback function

## -description

The <b>CalcPrivateDepthStencilStateSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a depth stencil state.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pDepthStencilDesc* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_ddi_depth_stencil_desc">D3D10_DDI_DEPTH_STENCIL_DESC</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

<b>CalcPrivateDepthStencilStateSize</b> returns the size of the memory region that the driver requires for creating a depth stencil state.

## -remarks



## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_ddi_depth_stencil_desc">D3D10_DDI_DEPTH_STENCIL_DESC</a>

