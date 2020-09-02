---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE
title: PFND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE (d3d10umddi.h)
description: Returns the number of bytes that the driver requires to store private data for the video decoder state.
old-location: display\calcprivatevideodecodersize.htm
ms.assetid: a878cba1-589e-4932-9d2b-1abab417660f
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE callback function"]
ms.keywords: CalcPrivateVideoDecoderSize, CalcPrivateVideoDecoderSize callback function [Display Devices], PFND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE, PFND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE callback, d3d10umddi/CalcPrivateVideoDecoderSize, display.calcprivatevideodecodersize
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
 - PFND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE
 - d3d10umddi/PFND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - CalcPrivateVideoDecoderSize
product:
 - Windows
---

# PFND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE callback function


## -description

Returns the number of bytes that the driver requires to store private data for the video decoder state.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pDecoder* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideodecoder">D3D11_1DDIARG_CREATEVIDEODECODER</a> structure that describes the video decoder.

## -returns

The required number of bytes for the video decoder state.

## -remarks

The runtime will validate the members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideodecoder">D3D11_1DDIARG_CREATEVIDEODECODER</a> structure before it calls this function.

This function is not expected to fail.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideodecoder">D3D11_1DDIARG_CREATEVIDEODECODER</a>

