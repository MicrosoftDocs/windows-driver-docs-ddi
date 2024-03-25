---
UID: NS:d3d10umddi.D3D10_1DDIARG_CREATESHADERRESOURCEVIEW
title: D3D10_1DDIARG_CREATESHADERRESOURCEVIEW (d3d10umddi.h)
description: The D3D10_1DDIARG_CREATESHADERRESOURCEVIEW structure describes the shader resource view to create.
old-location: display\d3d10_1ddiarg_createshaderresourceview.htm
ms.date: 11/03/2022
ms.custom: content-health
keywords: ["D3D10_1DDIARG_CREATESHADERRESOURCEVIEW structure"]
ms.keywords: D3D10_1DDIARG_CREATESHADERRESOURCEVIEW, D3D10_1DDIARG_CREATESHADERRESOURCEVIEW structure [Display Devices], UMDisplayDriver_Dx10param_Structs_a6468f32-7ebf-4ce8-b5c5-9163e65fce93.xml, d3d10umddi/D3D10_1DDIARG_CREATESHADERRESOURCEVIEW, display.d3d10_1ddiarg_createshaderresourceview
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista Service Pack 1 (SP1)
req.target-min-winversvr: Windows Server 2008
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
req.typenames: D3D10_1DDIARG_CREATESHADERRESOURCEVIEW
f1_keywords:
 - D3D10_1DDIARG_CREATESHADERRESOURCEVIEW
 - d3d10umddi/D3D10_1DDIARG_CREATESHADERRESOURCEVIEW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D10_1DDIARG_CREATESHADERRESOURCEVIEW
---

# D3D10_1DDIARG_CREATESHADERRESOURCEVIEW structure

## -description

The **D3D10_1DDIARG_CREATESHADERRESOURCEVIEW** structure describes the shader resource view to create.

## -struct-fields

### -field hDrvResource [in]

A handle to the shader resource.

### -field Format [in]

A DXGI_FORMAT-typed value that indicates the pixel format of the view.

### -field ResourceDimension [in]

A [**D3D10DDIRESOURCE_TYPE**](ne-d3d10umddi-d3d10ddiresource_type.md)-typed value that indicates the resource type and dimensionality.

### -field Buffer [in]

If the value in the **ResourceDimension** member is set to D3D10DDIRESOURCE_BUFFER, a member in the union that is contained in D3D10_1DDIARG_CREATESHADERRESOURCEVIEW that can hold a [**D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_buffer_shaderresourceview.md) structure for a buffer.

### -field Tex1D [in]

If the value in the **ResourceDimension** member is set to D3D10DDIRESOURCE_TEXTURE1D, a member in the union that is contained in D3D10_1DDIARG_CREATESHADERRESOURCEVIEW that can hold a [**D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_tex1d_shaderresourceview.md) structure for a one-dimensional texture.

### -field Tex2D [in]

If the value in the **ResourceDimension** member is set to D3D10DDIRESOURCE_TEXTURE2D, a member in the union that is contained in D3D10_1DDIARG_CREATESHADERRESOURCEVIEW that can hold a [**D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_tex2d_shaderresourceview.md) structure for a two-dimensional texture.

### -field Tex3D [in]

If the value in the **ResourceDimension** member is set to D3D10DDIRESOURCE_TEXTURE3D, a member in the union that is contained in D3D10_1DDIARG_CREATESHADERRESOURCEVIEW that can hold a [**D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_tex3d_shaderresourceview.md) structure for a three-dimensional texture.

### -field TexCube [in]

If the value in the **ResourceDimension** member is set to D3D10DDIRESOURCE_TEXTURECUBE, a member in the union that is contained in D3D10_1DDIARG_CREATESHADERRESOURCEVIEW that can hold a [**D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_texcube_shaderresourceview.md) structure for a cube texture.

## -remarks

[**CreateShaderResourceView(D3D10_1)**](nc-d3d10umddi-pfnd3d10_1ddi_createshaderresourceview.md) has a major functionality difference from the Direct3D 10.0 version (that is,[**CreateShaderResourceView**](nc-d3d10umddi-pfnd3d10ddi_createshaderresourceview.md)) in regard to the **ResourceDimension** member of D3D10_1DDIARG_CREATESHADERRESOURCEVIEW. If the Direct3D runtime attempts to create a view on a shader resource, **CreateShaderResourceView** requires that the **ResourceDimension** member of [**D3D10DDIARG_CREATESHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_createshaderresourceview.md) match the **ResourceDimension** member of [**D3D10DDIARG_CREATERESOURCE**](ns-d3d10umddi-d3d10ddiarg_createresource.md) for the shader resource that was created in a call to the driver's [**CreateResource(D3D10)**](nc-d3d10umddi-pfnd3d10ddi_createresource.md) function. If the Direct3D 10.1 runtime attempts to create a view on a shader resource, **CreateShaderResourceView(D3D10_1)** allows a slight relaxation for its **ResourceDimension** member. **CreateShaderResourceView(D3D10_1)** allows the creation of Tex2D views on TexCube resources. In addition, the distinction between TexCube at the resource level is gone in Direct3D version 10.1. **CreateShaderResourceView(D3D10_1)** only represents whether it can create a TexCube view. In Direct3D version 10.0, copying a resource, validation of a multiple render target, and so on (that is, various operations that required the resource type to be identical) all included the distinction of TexCube to factor into the resource type. In Direct3D version 10.1, the runtime can determine only Tex2D.

## -see-also

[**CalcPrivateShaderResourceViewSize(D3D10_1)**](nc-d3d10umddi-pfnd3d10_1ddi_calcprivateshaderresourceviewsize.md)

[**CreateShaderResourceView(D3D10_1)**](nc-d3d10umddi-pfnd3d10_1ddi_createshaderresourceview.md)

[**D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_buffer_shaderresourceview.md)

[**D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_tex1d_shaderresourceview.md)

[**D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_tex2d_shaderresourceview.md)

[**D3D10DDIARG_TEX3D_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_tex3d_shaderresourceview.md)

[**D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_texcube_shaderresourceview.md)

[**D3D10DDIRESOURCE_TYPE**](ne-d3d10umddi-d3d10ddiresource_type.md)
