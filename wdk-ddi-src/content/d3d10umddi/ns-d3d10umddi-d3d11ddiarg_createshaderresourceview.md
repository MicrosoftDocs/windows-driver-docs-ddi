---
UID: NS:d3d10umddi.D3D11DDIARG_CREATESHADERRESOURCEVIEW
title: D3D11DDIARG_CREATESHADERRESOURCEVIEW (d3d10umddi.h)
description: The D3D11DDIARG_CREATESHADERRESOURCEVIEW structure describes the shader resource view to create.
old-location: display\d3d11ddiarg_createshaderresourceview.htm
ms.date: 05/10/2018
keywords: ["D3D11DDIARG_CREATESHADERRESOURCEVIEW structure"]
ms.keywords: D3D11DDIARG_CREATESHADERRESOURCEVIEW, D3D11DDIARG_CREATESHADERRESOURCEVIEW structure [Display Devices], UMDisplayDriver_Dx11param_Structs_e1d9908f-af17-4d66-ba86-4782bb22458e.xml, d3d10umddi/D3D11DDIARG_CREATESHADERRESOURCEVIEW, display.d3d11ddiarg_createshaderresourceview
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
targetos: Windows
tech.root: display
req.typenames: D3D11DDIARG_CREATESHADERRESOURCEVIEW
f1_keywords:
 - D3D11DDIARG_CREATESHADERRESOURCEVIEW
 - d3d10umddi/D3D11DDIARG_CREATESHADERRESOURCEVIEW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D11DDIARG_CREATESHADERRESOURCEVIEW
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

[in] A <a href="/previous-versions/windows/hardware/drivers/ff541810(v=vs.85)">D3D10DDIRESOURCE_TYPE</a>-typed value that indicates the resource type and dimensionality.

### -field Buffer

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_BUFFER, a member in the union that is contained in D3D11DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_buffer_shaderresourceview">D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW</a> structure for a buffer.

### -field Tex1D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE1D, a member in the union that is contained in D3D11DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_tex1d_shaderresourceview">D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW</a> structure for a one-dimensional texture.

### -field Tex2D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE2D, a member in the union that is contained in D3D11DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_tex2d_shaderresourceview">D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW</a> structure for a two-dimensional texture.

### -field Tex3D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE3D, a member in the union that is contained in D3D11DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_tex3d_shaderresourceview">D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW</a> structure for a three-dimensional texture.

### -field TexCube

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURECUBE, a member in the union that is contained in D3D11DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_1ddiarg_texcube_shaderresourceview">D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW</a> structure for a cube texture.

### -field BufferEx

[in] If the value in the <b>ResourceDimension</b> member is set to D3D11DDIRESOURCE_BUFFEREX, a member in the union that is contained in D3D11DDIARG_CREATESHADERRESOURCEVIEW that can hold a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_bufferex_shaderresourceview">D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW</a> structure for a buffer.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivateshaderresourceviewsize">CalcPrivateShaderResourceViewSize(D3D11)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createshaderresourceview">CreateShaderResourceView(D3D11)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_buffer_shaderresourceview">D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_tex1d_shaderresourceview">D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_tex2d_shaderresourceview">D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_tex3d_shaderresourceview">D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW</a>



<a href="/previous-versions/windows/hardware/drivers/ff541810(v=vs.85)">D3D10DDIRESOURCE_TYPE</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_1ddiarg_texcube_shaderresourceview">D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_bufferex_shaderresourceview">D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW</a>
