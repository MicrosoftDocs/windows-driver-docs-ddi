---
UID: NS:d3d10umddi.D3D10DDIARG_CREATESHADERRESOURCEVIEW
title: D3D10DDIARG_CREATESHADERRESOURCEVIEW
author: windows-driver-content
description: The D3D10DDIARG_CREATESHADERRESOURCEVIEW structure describes the shader resource view to create.
old-location: display\d3d10ddiarg_createshaderresourceview.htm
old-project: display
ms.assetid: 60f0019b-ba02-433d-b5a2-f92a43f4d5a8
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3D10DDIARG_CREATESHADERRESOURCEVIEW, D3D10DDIARG_CREATESHADERRESOURCEVIEW structure [Display Devices], UMDisplayDriver_Dx10param_Structs_5307f7f2-0e25-4847-b1d4-5300c27320b7.xml, d3d10umddi/D3D10DDIARG_CREATESHADERRESOURCEVIEW, display.d3d10ddiarg_createshaderresourceview
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D10DDIARG_CREATESHADERRESOURCEVIEW
product: Windows
targetos: Windows
req.typenames: D3D10DDIARG_CREATESHADERRESOURCEVIEW
---

# D3D10DDIARG_CREATESHADERRESOURCEVIEW structure


## -description


The D3D10DDIARG_CREATESHADERRESOURCEVIEW structure describes the shader resource view to create.


## -struct-fields




### -field hDrvResource

[in] A handle to the shader resource. 


### -field Format

[in] A DXGI_FORMAT-typed value that indicates the pixel format of the view.


### -field ResourceDimension

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a>-typed value that indicates the resource type and dimensionality. 


### -field Buffer

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_BUFFER, a member in the union that is contained in D3D10DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541645">D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW</a> structure for a buffer. 


### -field Tex1D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE1D, a member in the union that is contained in D3D10DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541760">D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW</a> structure for a one-dimensional texture. 


### -field Tex2D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE2D, a member in the union that is contained in D3D10DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541773">D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW</a> structure for a two-dimensional texture. 


### -field Tex3D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE3D, a member in the union that is contained in D3D10DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541789">D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW</a> structure for a three-dimensional texture. 


### -field TexCube

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURECUBE, a member in the union that is contained in D3D10DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541807">D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW</a> structure for a cube texture. 


## -see-also




<a href="https://msdn.microsoft.com/2abf5ca9-974b-40d7-b71c-43c4fb33dd7c">CalcPrivateShaderResourceViewSize</a>



<a href="https://msdn.microsoft.com/3b1c998d-3fde-4712-ba74-7c8033033182">CreateShaderResourceView</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541645">D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541760">D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541773">D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541789">D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541807">D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a>
 

 

