---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATERASTERIZERSTATESIZE
title: PFND3D11_1DDI_CALCPRIVATERASTERIZERSTATESIZE (d3d10umddi.h)
description: Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a rasterizer state.
old-location: display\calcprivaterasterizerstatesize_d3d11_1_.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_CALCPRIVATERASTERIZERSTATESIZE callback function"]
ms.keywords: CalcPrivateRasterizerStateSize(D3D11_1), CalcPrivateRasterizerStateSize(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_CALCPRIVATERASTERIZERSTATESIZE, PFND3D11_1DDI_CALCPRIVATERASTERIZERSTATESIZE callback, d3d10umddi/CalcPrivateRasterizerStateSize(D3D11_1), display.calcprivaterasterizerstatesize_d3d11_1_, display.pfncalcprivaterasterizerstatesize
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D11_1DDI_CALCPRIVATERASTERIZERSTATESIZE
 - d3d10umddi/PFND3D11_1DDI_CALCPRIVATERASTERIZERSTATESIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - PFND3D11_1DDI_CALCPRIVATERASTERIZERSTATESIZE
---

# PFND3D11_1DDI_CALCPRIVATERASTERIZERSTATESIZE callback function


## -description

Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a rasterizer state.

## -parameters

### -param unnamedParam1

*hDevice* [in]

A handle to the display device (graphics context).

### -param unnamedParam2

*pRasterizerDesc* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1_ddi_rasterizer_desc">D3D11_1_DDI_RASTERIZER_DESC</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

The size of the memory region that the driver requires for creating a rasterizer state.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1_ddi_rasterizer_desc">D3D11_1_DDI_RASTERIZER_DESC</a>

