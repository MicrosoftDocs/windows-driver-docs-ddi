---
UID: NS:d3d10umddi.D3DWDDM2_0DDIARG_CREATESHADERRESOURCEVIEW
tech.root: display
title: D3DWDDM2_0DDIARG_CREATESHADERRESOURCEVIEW
ms.date: 06/02/2023
targetos: Windows
description: Learn more about the D3DWDDM2_0DDIARG_CREATESHADERRESOURCEVIEW structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d10umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows (WDDM 2.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DWDDM2_0DDIARG_CREATESHADERRESOURCEVIEW
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3DWDDM2_0DDIARG_CREATESHADERRESOURCEVIEW
f1_keywords:
 - D3DWDDM2_0DDIARG_CREATESHADERRESOURCEVIEW
 - d3d10umddi/D3DWDDM2_0DDIARG_CREATESHADERRESOURCEVIEW
dev_langs:
 - c++
helpviewer_keywords:
 - D3DWDDM2_0DDIARG_CREATESHADERRESOURCEVIEW
---

## -description

The **D3DWDDM2_0DDIARG_CREATESHADERRESOURCEVIEW** structure describes a shader resource view.

## -struct-fields

### -field hDrvResource

[in] A handle to the shader resource.

### -field Format

[in] A [**DXGI_FORMAT**](/windows/win32/api/dxgiformat/ne-dxgiformat-dxgi_format)-typed value that indicates the pixel format of the view.

### -field ResourceDimension

[in] A [**D3D10DDIRESOURCE_TYPE**](ne-d3d10umddi-d3d10ddiresource_type.md)-typed value that indicates the resource type and dimensionality.

### -field Buffer

[in] If **ResourceDimension** is set to D3D10DDIRESOURCE_BUFFER, **Buffer** holds a [**D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_buffer_shaderresourceview.md) structure for a buffer.

### -field Tex1D

[in] If **ResourceDimension** is set to D3D10DDIRESOURCE_TEXTURE1D, holds a [**D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_tex1d_shaderresourceview.md) structure for a one-dimensional texture.

### -field Tex2D

[in] If **ResourceDimension** is set to D3D10DDIRESOURCE_TEXTURE2D, **Buffer** holds a [**D3DWDDM2_0DDIARG_TEX2D_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3dwddm2_0ddiarg_tex2d_shaderresourceview.md) structure for a two-dimensional texture.

### -field Tex3D

[in] If **ResourceDimension** is set to D3D10DDIRESOURCE_TEXTURE3D, **Buffer** holds a [**D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_tex3d_shaderresourceview.md) structure for a three-dimensional texture.

### -field TexCube

[in] If **ResourceDimension** is set to D3D10DDIRESOURCE_TEXTURECUBE, **Buffer** holds a [**D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_texcube_shaderresourceview.md) structure for a cube texture.

### -field BufferEx

[in] If **ResourceDimension** is set to D3D11DDIRESOURCE_BUFFEREX, a **Buffer** holds a [**D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d11ddiarg_bufferex_shaderresourceview.md) structure for a buffer.

## -see-also

[**CalcPrivateShaderResourceViewSize(WDDM 2.0)**](nc-d3d10umddi-pfnd3dwddm2_0ddi_calcprivateshaderresourceviewsize.md)

[**CreateShaderResourceView(WDDM 2.0)**](nc-d3d10umddi-pfnd3dwddm2_0ddi_createshaderresourceview.md)

[**D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_buffer_shaderresourceview.md)

[**D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_tex1d_shaderresourceview.md)

[**D3DWDDM2_0DDIARG_TEX2D_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3dwddm2_0ddiarg_tex2d_shaderresourceview.md)

[**D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_tex3d_shaderresourceview.md)

[**D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_texcube_shaderresourceview.md)

[**D3D10DDIRESOURCE_TYPE**](ne-d3d10umddi-d3d10ddiresource_type.md)

[**D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d11ddiarg_bufferex_shaderresourceview.md)