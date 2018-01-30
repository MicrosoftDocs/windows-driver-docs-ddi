---
UID: NS:d3dumddi._D3DDDIARG_SETCONVOLUTIONKERNELMONO
title: "_D3DDDIARG_SETCONVOLUTIONKERNELMONO"
author: windows-driver-content
description: The D3DDDIARG_SETCONVOLUTIONKERNELMONO structure describes parameters for setting the monochrome convolution kernel.
old-location: display\d3dddiarg_setconvolutionkernelmono.htm
old-project: display
ms.assetid: 6a7a19c7-2e2d-4e52-920d-68f1d2d77585
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDIARG_SETCONVOLUTIONKERNELMONO structure [Display Devices], display.d3dddiarg_setconvolutionkernelmono, UMDisplayDriver_param_Structs_57045815-ecbd-4b5f-a94d-5bbf189449f2.xml, d3dumddi/D3DDDIARG_SETCONVOLUTIONKERNELMONO, _D3DDDIARG_SETCONVOLUTIONKERNELMONO, D3DDDIARG_SETCONVOLUTIONKERNELMONO
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_SETCONVOLUTIONKERNELMONO
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_SETCONVOLUTIONKERNELMONO
---

# _D3DDDIARG_SETCONVOLUTIONKERNELMONO structure


## -description


The D3DDDIARG_SETCONVOLUTIONKERNELMONO structure describes parameters for setting the monochrome convolution kernel. 


## -syntax


````
typedef struct _D3DDDIARG_SETCONVOLUTIONKERNELMONO {
  UINT  Width;
  UINT  Height;
  FLOAT *pKernelRow;
  FLOAT *pKernelCol;
} D3DDDIARG_SETCONVOLUTIONKERNELMONO;
````


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

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setconvolutionkernelmono.md">SetConvolutionKernelMono</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_SETCONVOLUTIONKERNELMONO structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

