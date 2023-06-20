---
UID: NS:d3d10umddi.D3DWDDM2_0DDIARG_CREATEUNORDEREDACCESSVIEW
tech.root: display
title: D3DWDDM2_0DDIARG_CREATEUNORDEREDACCESSVIEW
ms.date: 06/02/2023
targetos: Windows
description: Learn more about the D3DWDDM2_0DDIARG_CREATEUNORDEREDACCESSVIEW structure.
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
req.target-min-winverclnt: Windows 10 (WDDM 2.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DWDDM2_0DDIARG_CREATEUNORDEREDACCESSVIEW
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
 - D3DWDDM2_0DDIARG_CREATEUNORDEREDACCESSVIEW
f1_keywords:
 - D3DWDDM2_0DDIARG_CREATEUNORDEREDACCESSVIEW
 - d3d10umddi/D3DWDDM2_0DDIARG_CREATEUNORDEREDACCESSVIEW
dev_langs:
 - c++
helpviewer_keywords:
 - D3DWDDM2_0DDIARG_CREATEUNORDEREDACCESSVIEW
---

## -description

The **D3DWDDM2_0DDIARG_CREATEUNORDEREDACCESSVIEW** structure describes an unordered access view that is used to create a shader resource view in a call to [**CreateUnorderedAccessView (WDDM 2.0)**](nc-d3d10umddi-pfnd3dwddm2_0ddi_createunorderedaccessview.md).

## -struct-fields

### -field hDrvResource

[in] A handle to the unordered access block.

### -field Format

[in] A [**DXGI_FORMAT**](/windows/win32/api/dxgiformat/ne-dxgiformat-dxgi_format)-typed value that indicates the pixel format of the unordered access block.

### -field ResourceDimension

A [**D3D10DDIRESOURCE_TYPE**](ne-d3d10umddi-d3d10ddiresource_type.md)-typed value that indicates the resource type and dimensionality of the unordered access block. The Direct3D runtime will never set **ResourceDimension** to D3D10DDIRESOURCE_TEXTURECUBE.

### -field Buffer

[in] If **ResourceDimension** is set to D3D10DDIRESOURCE_BUFFER, **Buffer** holds a [**D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW**](ns-d3d10umddi-d3d11ddiarg_buffer_unorderedaccessview.md) structure for a buffer.

### -field Tex1D

[in] If **ResourceDimension** is set to D3D10DDIRESOURCE_TEXTURE1D, **Tex1D** holds a [**D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW**](ns-d3d10umddi-d3d11ddiarg_tex1d_unorderedaccessview.md) structure for a one-dimensional texture.

### -field Tex2D

[in] If **ResourceDimension** is set to D3D10DDIRESOURCE_TEXTURE2D, **Tex2D** holds a [**D3DWDDM2_0DDIARG_TEX2D_UNORDEREDACCESSVIEW**](ns-d3d10umddi-d3dwddm2_0ddiarg_tex2d_unorderedaccessview.md) structure for a two-dimensional texture.

### -field Tex3D

[in] If **ResourceDimension** is set to D3D10DDIRESOURCE_TEXTURE3D, **Tex3D** holds a [**D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW**](ns-d3d10umddi-d3d11ddiarg_tex3d_unorderedaccessview.md) structure for a three-dimensional texture.

## -see-also

[**CalcPrivateShaderResourceViewSize (WDDM 2.0)**](nc-d3d10umddi-pfnd3dwddm2_0ddi_calcprivateunorderedaccessviewsize.md)

[**CreateUnorderedAccessView (WDDM 2.0)**](nc-d3d10umddi-pfnd3dwddm2_0ddi_createunorderedaccessview.md)

[**D3D10DDIRESOURCE_TYPE**](ne-d3d10umddi-d3d10ddiresource_type.md)

[**D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW**](ns-d3d10umddi-d3d11ddiarg_buffer_unorderedaccessview.md)

[**D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW**](ns-d3d10umddi-d3d11ddiarg_tex1d_unorderedaccessview.md)

[**D3DWDDM2_0DDIARG_TEX2D_UNORDEREDACCESSVIEW**](ns-d3d10umddi-d3dwddm2_0ddiarg_tex2d_unorderedaccessview.md)

[**D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW**](ns-d3d10umddi-d3d11ddiarg_tex3d_unorderedaccessview.md)