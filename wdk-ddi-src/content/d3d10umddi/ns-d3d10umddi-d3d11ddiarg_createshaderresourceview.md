---
UID: NS:d3d10umddi.D3D11DDIARG_CREATESHADERRESOURCEVIEW
title: D3D11DDIARG_CREATESHADERRESOURCEVIEW
author: windows-driver-content
description: The D3D11DDIARG_CREATESHADERRESOURCEVIEW structure describes the shader resource view to create.
old-location: display\d3d11ddiarg_createshaderresourceview.htm
old-project: display
ms.assetid: 0271e937-a55d-4153-b1e1-045fef4b76a0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11DDIARG_CREATESHADERRESOURCEVIEW, D3D11DDIARG_CREATESHADERRESOURCEVIEW structure [Display Devices], UMDisplayDriver_Dx11param_Structs_e1d9908f-af17-4d66-ba86-4782bb22458e.xml, d3d10umddi/D3D11DDIARG_CREATESHADERRESOURCEVIEW, display.d3d11ddiarg_createshaderresourceview
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_CREATESHADERRESOURCEVIEW is supported beginning with the Windows 7 operating system.
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
-	D3D11DDIARG_CREATESHADERRESOURCEVIEW
product: Windows
targetos: Windows
req.typenames: D3D11DDIARG_CREATESHADERRESOURCEVIEW
---

# D3D11DDIARG_CREATESHADERRESOURCEVIEW structure


## -description


The D3D11DDIARG_CREATESHADERRESOURCEVIEW structure describes the shader resource view to create.


## -struct-fields




### -field hDrvResource

[in] A handle to the shader resource. 


### -field Format

[in] A DXGI_FORMAT-typed value that indicates the pixel format of the view.


### -field ResourceDimension

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a>-typed value that indicates the resource type and dimensionality. 


#### - Buffer

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_BUFFER, a member in the union that is contained in D3D11DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541645">D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW</a> structure for a buffer. 


#### - BufferEx

[in] If the value in the <b>ResourceDimension</b> member is set to D3D11DDIRESOURCE_BUFFEREX, a member in the union that is contained in D3D11DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542025">D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW</a> structure for a buffer. 


#### - Tex1D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE1D, a member in the union that is contained in D3D11DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541760">D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW</a> structure for a one-dimensional texture. 


#### - Tex2D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE2D, a member in the union that is contained in D3D11DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541773">D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW</a> structure for a two-dimensional texture. 


#### - Tex3D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE3D, a member in the union that is contained in D3D11DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541789">D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW</a> structure for a three-dimensional texture. 


#### - TexCube

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURECUBE, a member in the union that is contained in D3D11DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541865">D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW</a> structure for a cube texture. 


## -see-also




<a href="https://msdn.microsoft.com/894f6ef1-a5a4-40aa-9a07-f66da4ce7d81">CalcPrivateShaderResourceViewSize(D3D11)</a>



<a href="https://msdn.microsoft.com/7ca462c7-ec43-4af7-92c8-ed69e5d324e2">CreateShaderResourceView(D3D11)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541645">D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541760">D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541773">D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541789">D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541865">D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542025">D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW</a>
 

 

