---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE
title: PFND3D10DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE (d3d10umddi.h)
description: The CalcPrivateDepthStencilViewSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a depth stencil view.
old-location: display\calcprivatedepthstencilviewsize.htm
ms.assetid: e5dfa018-f9a5-467f-8e84-9697d5f94689
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE callback function"]
ms.keywords: CalcPrivateDepthStencilViewSize, CalcPrivateDepthStencilViewSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE, PFND3D10DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE callback, UserModeDisplayDriverDx10_Functions_514ed3bc-fc1d-4bda-bcc9-f90e6900c002.xml, d3d10umddi/CalcPrivateDepthStencilViewSize, display.calcprivatedepthstencilviewsize
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

# PFND3D10DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE callback function

## -description

The <b>CalcPrivateDepthStencilViewSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a depth stencil view.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateDepthStencilView* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdepthstencilview">D3D10DDIARG_CREATEDEPTHSTENCILVIEW</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

<b>CalcPrivateDepthStencilViewSize</b> returns the size of the memory region that the driver requires for creating a depth stencil view.

## -remarks



## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdepthstencilview">D3D10DDIARG_CREATEDEPTHSTENCILVIEW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>

