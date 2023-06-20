---
UID: NS:d3d10umddi.D3D11DDIARG_CREATESHADERRESOURCEVIEW
title: D3D11DDIARG_CREATESHADERRESOURCEVIEW (d3d10umddi.h)
description: Learn more about the D3D11DDIARG_CREATESHADERRESOURCEVIEW structure.
ms.date: 06/02/2023
ms.custom: content-health
keywords: ["D3D11DDIARG_CREATESHADERRESOURCEVIEW structure"]
ms.keywords: D3D11DDIARG_CREATESHADERRESOURCEVIEW, D3D11DDIARG_CREATESHADERRESOURCEVIEW structure [Display Devices], UMDisplayDriver_Dx11param_Structs_e1d9908f-af17-4d66-ba86-4782bb22458e.xml, d3d10umddi/D3D11DDIARG_CREATESHADERRESOURCEVIEW, display.d3d11ddiarg_createshaderresourceview
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 7
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

The **D3D11DDIARG_CREATESHADERRESOURCEVIEW** structure describes the shader resource view to create.

## -struct-fields

### -field hDrvResource [in]

A handle to the shader resource.

### -field Format

[in] A [**DXGI_FORMAT**](/windows/win32/api/dxgiformat/ne-dxgiformat-dxgi_format)-typed value that indicates the pixel format of the view.

### -field ResourceDimension [in]

A [**D3D10DDIRESOURCE_TYPE**](ne-d3d10umddi-d3d10ddiresource_type.md)-typed value that indicates the resource type and dimensionality.

### -field Buffer [in]

If **ResourceDimension** is set to D3D10DDIRESOURCE_BUFFER, **Buffer** holds a [**D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_buffer_shaderresourceview.md) structure for a buffer.

### -field Tex1D [in]

If **ResourceDimension** is set to D3D10DDIRESOURCE_TEXTURE1D, **Buffer** holds a [**D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_tex1d_shaderresourceview.md) structure for a one-dimensional texture.

### -field Tex2D [in]

If **ResourceDimension** is set to D3D10DDIRESOURCE_TEXTURE2D, **Buffer** holds a [**D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_tex2d_shaderresourceview.md) structure for a two-dimensional texture.

### -field Tex3D [in]

If **ResourceDimension** is set to D3D10DDIRESOURCE_TEXTURE3D, **Buffer** holds a [**D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_tex3d_shaderresourceview.md) structure for a three-dimensional texture.

### -field TexCube [in]

If **ResourceDimension** is set to D3D10DDIRESOURCE_TEXTURECUBE, **Buffer** holds a [**D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_texcube_shaderresourceview.md) structure for a cube texture.

### -field BufferEx [in]

If **ResourceDimension** is set to D3D11DDIRESOURCE_BUFFEREX, a **Buffer** holds a [**D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d11ddiarg_bufferex_shaderresourceview.md) structure for a buffer.

## -see-also

[**CalcPrivateShaderResourceViewSize(D3D11)**](nc-d3d10umddi-pfnd3d11ddi_calcprivateshaderresourceviewsize.md)

[**CreateShaderResourceView(D3D11)**](nc-d3d10umddi-pfnd3d11ddi_createshaderresourceview.md)

[**D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_buffer_shaderresourceview.md)

[**D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_tex1d_shaderresourceview.md)

[**D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_tex2d_shaderresourceview.md)

[**D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_tex3d_shaderresourceview.md)

[**D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_texcube_shaderresourceview.md)

[**D3D10DDIRESOURCE_TYPE**](ne-d3d10umddi-d3d10ddiresource_type.md)

[**D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d11ddiarg_bufferex_shaderresourceview.md)
