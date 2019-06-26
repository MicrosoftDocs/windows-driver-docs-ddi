---
UID: NS:d3dumddi._D3DDDIARG_SETCONVOLUTIONKERNELMONO
title: _D3DDDIARG_SETCONVOLUTIONKERNELMONO (d3dumddi.h)
description: The D3DDDIARG_SETCONVOLUTIONKERNELMONO structure describes parameters for setting the monochrome convolution kernel.
old-location: display\d3dddiarg_setconvolutionkernelmono.htm
tech.root: display
ms.assetid: 6a7a19c7-2e2d-4e52-920d-68f1d2d77585
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_SETCONVOLUTIONKERNELMONO, D3DDDIARG_SETCONVOLUTIONKERNELMONO structure [Display Devices], UMDisplayDriver_param_Structs_57045815-ecbd-4b5f-a94d-5bbf189449f2.xml, _D3DDDIARG_SETCONVOLUTIONKERNELMONO, d3dumddi/D3DDDIARG_SETCONVOLUTIONKERNELMONO, display.d3dddiarg_setconvolutionkernelmono
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDIARG_SETCONVOLUTIONKERNELMONO
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_SETCONVOLUTIONKERNELMONO
---

# _D3DDDIARG_SETCONVOLUTIONKERNELMONO structure


## -description


The D3DDDIARG_SETCONVOLUTIONKERNELMONO structure describes parameters for setting the monochrome convolution kernel. 


## -struct-fields




### -field Width

[in] The width, which is the resolution of the filter kernel in the horizontal direction. Valid values for this member are from 1 to 7. 


### -field Height

[in] The height, which is the resolution of the filter kernel in the vertical direction. Valid values for this member are from 1 to 7. 


### -field pKernelRow

[in] A pointer to weights in the horizontal direction of a separable filter. In Microsoft Direct3D 9.L and later, <b>pKernelRow</b> must be <b>NULL</b>, which indicates that all of the weights are 1.0. 


### -field pKernelCol

[in] A pointer to weights in the vertical direction of a separable filter. In Direct3D 9.L and later, <b>pKernelCol</b> must be <b>NULL</b>, which indicates that all of the weights are 1.0. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_setconvolutionkernelmono">SetConvolutionKernelMono</a>
 

 

