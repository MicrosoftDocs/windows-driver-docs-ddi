---
UID: NS:d3d10umddi.D3D10DDIARG_CREATESHADERRESOURCEVIEW
title: D3D10DDIARG_CREATESHADERRESOURCEVIEW
author: windows-driver-content
description: The D3D10DDIARG_CREATESHADERRESOURCEVIEW structure describes the shader resource view to create.
old-location: display\d3d10ddiarg_createshaderresourceview.htm
old-project: display
ms.assetid: 60f0019b-ba02-433d-b5a2-f92a43f4d5a8
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.d3d10ddiarg_createshaderresourceview, D3D10DDIARG_CREATESHADERRESOURCEVIEW, D3D10DDIARG_CREATESHADERRESOURCEVIEW structure [Display Devices], UMDisplayDriver_Dx10param_Structs_5307f7f2-0e25-4847-b1d4-5300c27320b7.xml, d3d10umddi/D3D10DDIARG_CREATESHADERRESOURCEVIEW
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3D10DDIARG_CREATESHADERRESOURCEVIEW
product: Windows
targetos: Windows
req.typenames: D3D10DDIARG_CREATESHADERRESOURCEVIEW
---

# D3D10DDIARG_CREATESHADERRESOURCEVIEW structure


## -description


The D3D10DDIARG_CREATESHADERRESOURCEVIEW structure describes the shader resource view to create.


## -syntax


````
typedef struct D3D10DDIARG_CREATESHADERRESOURCEVIEW {
  D3D10DDI_HRESOURCE    hDrvResource;
  DXGI_FORMAT           Format;
  D3D10DDIRESOURCE_TYPE ResourceDimension;
  union {
    D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW  Buffer;
    D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW   Tex1D;
    D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW   Tex2D;
    D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW   Tex3D;
    D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW TexCube;
  };
} D3D10DDIARG_CREATESHADERRESOURCEVIEW;
````


## -struct-fields




### -field hDrvResource

[in] A handle to the shader resource. 


### -field Format

[in] A DXGI_FORMAT-typed value that indicates the pixel format of the view.


### -field ResourceDimension

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a>-typed value that indicates the resource type and dimensionality. 


#### - Buffer

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_BUFFER, a member in the union that is contained in D3D10DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_buffer_shaderresourceview.md">D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW</a> structure for a buffer. 


#### - Tex1D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE1D, a member in the union that is contained in D3D10DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_tex1d_shaderresourceview.md">D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW</a> structure for a one-dimensional texture. 


#### - Tex2D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE2D, a member in the union that is contained in D3D10DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_tex2d_shaderresourceview.md">D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW</a> structure for a two-dimensional texture. 


#### - Tex3D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE3D, a member in the union that is contained in D3D10DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_tex3d_shaderresourceview.md">D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW</a> structure for a three-dimensional texture. 


#### - TexCube

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURECUBE, a member in the union that is contained in D3D10DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_texcube_shaderresourceview.md">D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW</a> structure for a cube texture. 


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createshaderresourceview.md">CreateShaderResourceView</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_tex2d_shaderresourceview.md">D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_tex1d_shaderresourceview.md">D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateshaderresourceviewsize.md">CalcPrivateShaderResourceViewSize</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateshaderresourceviewsize.md">CalcPrivateShaderResourceViewSize</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_buffer_shaderresourceview.md">D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_tex3d_shaderresourceview.md">D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_CREATESHADERRESOURCEVIEW structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

