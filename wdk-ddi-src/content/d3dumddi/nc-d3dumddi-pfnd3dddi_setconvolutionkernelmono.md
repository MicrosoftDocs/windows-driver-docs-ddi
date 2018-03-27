---
UID: NC:d3dumddi.PFND3DDDI_SETCONVOLUTIONKERNELMONO
title: PFND3DDDI_SETCONVOLUTIONKERNELMONO
author: windows-driver-content
description: The SetConvolutionKernelMono function defines the resolution and weights of the kernel filter, which is used when the D3DTEXF_CONVOLUTIONMONO texture filtering mode is set.
old-location: display\setconvolutionkernelmono.htm
old-project: display
ms.assetid: b560352f-ca4e-4f03-88ac-13ec080834aa
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_SETCONVOLUTIONKERNELMONO, SetConvolutionKernelMono, SetConvolutionKernelMono callback function [Display Devices], UserModeDisplayDriver_Functions_488a5fdd-562a-475b-a86d-23d05f35c6dc.xml, d3dumddi/SetConvolutionKernelMono, display.setconvolutionkernelmono
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	SetConvolutionKernelMono
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SETCONVOLUTIONKERNELMONO callback


## -description


The <i>SetConvolutionKernelMono</i> function defines the resolution and weights of the kernel filter, which is used when the D3DTEXF_CONVOLUTIONMONO texture filtering mode is set.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543285">D3DDDIARG_SETCONVOLUTIONKERNELMONO</a> structure that describes parameters for setting the monochrome convolution kernel.


## -returns



<i>SetConvolutionKernelMono</i> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The monochrome convolution kernel is successfully set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>SetConvolutionKernelMono</i> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -remarks



D3DTEXF_CONVOLUTIONMONO is a texture filter mode that is used for sampling monochrome textures (that is, textures that are formatted as one bit per pixel (D3DDDIFMT_A1)). In the Direct3D 9.L runtime, the convolution filter is a two-dimensional box filter (that is, all weights = 1.0). However, the <i>SetConvolutionKernelMono</i> function is defined to support a more general filter. When D3DTEXF_CONVOLUTIONMONO is set to a texture sampler, the texture sampler states D3DTSS_MIPFILTER, D3DTSS_MINFILTER and D3DTSS_MAGFILTER are ignored. The texture address D3DTADDRESS_BORDER with border color 0 should be applied in this filtering mode. The user-mode display driver should return an error or ignore the rendered primitive if this filtering mode is used with a non-monochrome texture.

The following formula is used to perform the convolution:

Result = Sum(i=0, i &lt;N<sub>v</sub>)[ (R<sub>i</sub>*(1 - alpha) + R<sub>i+1</sub>*alpha) * S)]

Rₖ = Sum(j=0, j &lt;N<sub>u</sub>)[T<sub>k,j</sub>*(1 - beta) + T<sub>k,j+1</sub>*beta],  where 0 &lt; k &lt; N<sub>v</sub>

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543285">D3DDDIARG_SETCONVOLUTIONKERNELMONO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETCONVOLUTIONKERNELMONO callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

