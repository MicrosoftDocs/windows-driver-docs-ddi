---
UID: NE:d3d10umddi.D3D10DDIRESOURCE_TYPE
tech.root: display
title: D3D10DDIRESOURCE_TYPE
ms.date: 06/02/2023
targetos: Windows
description: Learn more about the D3D10DDIRESOURCE_TYPE enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d10umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D10DDIRESOURCE_TYPE
f1_keywords:
 - D3D10DDIRESOURCE_TYPE
 - d3d10umddi/D3D10DDIRESOURCE_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - D3D10DDIRESOURCE_TYPE
---

## -description

The **D3D10DDIRESOURCE_TYPE** enumeration identifies the type of a resource.

## -enum-fields

### -field D3D10DDIRESOURCE_BUFFER

The resource is a buffer.

### -field D3D10DDIRESOURCE_TEXTURE1D

The resource is a one-dimensional texture.

### -field D3D10DDIRESOURCE_TEXTURE2D

The resource is a two-dimensional texture.

### -field D3D10DDIRESOURCE_TEXTURE3D

The resource is a three-dimensional texture.

### -field D3D10DDIRESOURCE_TEXTURECUBE

The resource is a cube texture.

### -field D3D11DDIRESOURCE_BUFFEREX

The texture is an expanded buffer. Supported starting in Windows 7.

## -see-also

[**D3D10DDIARG_CREATERESOURCE**](ns-d3d10umddi-d3d10ddiarg_createresource.md)

[**D3D10DDIARG_CREATEDEPTHSTENCILVIEW**](ns-d3d10umddi-d3d10ddiarg_createdepthstencilview.md)

[**D3D10DDIARG_CREATESHADERRESOURCEVIEW**](ns-d3d10umddi-d3d10ddiarg_createshaderresourceview.md)

[**D3D11DDIARG_CREATESHADERRESOURCEVIEW**](ns-d3d10umddi-d3d11ddiarg_createshaderresourceview.md)

[**D3D11DDIARG_CREATEUNORDEREDACCESSVIEW**](ns-d3d10umddi-d3d11ddiarg_createunorderedaccessview.md)

[**D3DWDDM2_0DDIARG_CREATESHADERRESOURCEVIEW**](ns-d3d10umddi-d3dwddm2_0ddiarg_createshaderresourceview.md)

[**D3DWDDM2_0DDIARG_CREATEUNORDEREDACCESSVIEW**](ns-d3d10umddi-d3dwddm2_0ddiarg_createunorderedaccessview.md)
