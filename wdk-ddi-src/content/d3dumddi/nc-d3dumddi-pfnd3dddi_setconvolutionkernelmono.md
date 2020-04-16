---
UID: NC:d3dumddi.PFND3DDDI_SETCONVOLUTIONKERNELMONO
title: PFND3DDDI_SETCONVOLUTIONKERNELMONO (d3dumddi.h)
description: The SetConvolutionKernelMono function defines the resolution and weights of the kernel filter, which is used when the D3DTEXF_CONVOLUTIONMONO texture filtering mode is set.
old-location: display\setconvolutionkernelmono.htm
tech.root: display
ms.assetid: b560352f-ca4e-4f03-88ac-13ec080834aa
ms.date: 05/10/2018
keywords: ["PFND3DDDI_SETCONVOLUTIONKERNELMONO callback function"]
ms.keywords: PFND3DDDI_SETCONVOLUTIONKERNELMONO, PFND3DDDI_SETCONVOLUTIONKERNELMONO callback, SetConvolutionKernelMono, SetConvolutionKernelMono callback function [Display Devices], UserModeDisplayDriver_Functions_488a5fdd-562a-475b-a86d-23d05f35c6dc.xml, d3dumddi/SetConvolutionKernelMono, display.setconvolutionkernelmono
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.typenames: 
f1_keywords:
 - "d3dumddi/SetConvolutionKernelMono"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - SetConvolutionKernelMono
product:
 - Windows
---

# PFND3DDDI_SETCONVOLUTIONKERNELMONO callback function

## -description

The <i>SetConvolutionKernelMono</i> function defines the resolution and weights of the kernel filter, which is used when the D3DTEXF_CONVOLUTIONMONO texture filtering mode is set.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setconvolutionkernelmono">D3DDDIARG_SETCONVOLUTIONKERNELMONO</a> structure that describes parameters for setting the monochrome convolution kernel.

## -returns

<i>SetConvolutionKernelMono</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The monochrome convolution kernel is successfully set.|
|E_OUTOFMEMORY|SetConvolutionKernelMono could not allocate the required memory for it to complete.|

## -remarks

D3DTEXF_CONVOLUTIONMONO is a texture filter mode that is used for sampling monochrome textures (that is, textures that are formatted as one bit per pixel (D3DDDIFMT_A1)). In the Direct3D 9.L runtime, the convolution filter is a two-dimensional box filter (that is, all weights = 1.0). However, the <i>SetConvolutionKernelMono</i> function is defined to support a more general filter. When D3DTEXF_CONVOLUTIONMONO is set to a texture sampler, the texture sampler states D3DTSS_MIPFILTER, D3DTSS_MINFILTER and D3DTSS_MAGFILTER are ignored. The texture address D3DTADDRESS_BORDER with border color 0 should be applied in this filtering mode. The user-mode display driver should return an error or ignore the rendered primitive if this filtering mode is used with a non-monochrome texture.

The following formula is used to perform the convolution:

Result = Sum(i=0, i <N<sub>v</sub>)[ (R<sub>i</sub>*(1 - alpha) + R<sub>i+1</sub>*alpha) * S)]

Rₖ = Sum(j=0, j <N<sub>u</sub>)[T<sub>k,j</sub>*(1 - beta) + T<sub>k,j+1</sub>*beta],  where 0 < k < N<sub>v</sub>

S = 1 / (N<sub>u</sub> * N<sub>v</sub>)

N<sub>u</sub> and N<sub>v</sub> are the width and height of the filter kernel.

T<sub>i,j</sub> are texture samples from a monochrome texture at location (i, j).

The precision of the filter operations must be at least 6 bits.

The interpolated texture coordinate values (U, V) at a pixel center are the coordinates of the center of the filter kernel.

The coordinates of the upper left filter kernel sample (U<sub>f</sub>,V<sub>f</sub>) are computed as:

U<sub>f</sub> = U * TextureWidth - N<sub>u</sub> * 0.5

V<sub>f </sub>= V * TextureHeight - N<sub>v</sub> * 0.5

Then

beta = U<sub>f</sub> - truncate(U<sub>f</sub>)

alpha = V<sub>f</sub> - truncate(V<sub>f</sub>)

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setconvolutionkernelmono">D3DDDIARG_SETCONVOLUTIONKERNELMONO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

