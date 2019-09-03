---
UID: NE:d3dumddi._D3DDDITEXTURESTAGESTATETYPE
title: _D3DDDITEXTURESTAGESTATETYPE (d3dumddi.h)
description: The texture stage state type.
ms.assetid: 7da9bfc3-f8e1-4898-9f12-f87ea1a1450f
ms.date: 10/19/2018
ms.topic: enum
f1_keywords:
 - "d3dumddi/_D3DDDITEXTURESTAGESTATETYPE"
ms.keywords: _D3DDDITEXTURESTAGESTATETYPE, D3DDDITEXTURESTAGESTATETYPE, 
req.header: d3dumddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3DDDITEXTURESTAGESTATETYPE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dumddi.h
api_name: 
- _D3DDDITEXTURESTAGESTATETYPE
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# _D3DDDITEXTURESTAGESTATETYPE enumeration

## -description

The texture stage state type.

## -enum-fields

### -field D3DDDITSS_TEXTUREMAP 

A [D3DTEXTUREOP](../d3d9types/ne-d3d9types-_d3dtextureop.md) that specifies the texture map.

### -field D3DDDITSS_COLOROP 

A D3DTEXTUREOP that specifies per-stage blending controls for color channels.

### -field D3DDDITSS_COLORARG1 

A D3DTA_TEXTURE that represents texture arguments. The D3DTA_TEXTURE constant is used to select a texture color.

### -field D3DDDITSS_COLORARG2 

A D3DTA_TEXTURE that represents texture arguments. The D3DTA_TEXTURE constant is used to select a texture color.

### -field D3DDDITSS_ALPHAOP 

A D3DTEXTUREOP that specifies per-stage blending controls for alpha channel.

### -field D3DDDITSS_ALPHAARG1 

A D3DTA_TEXTURE that represents texture arguments. The D3DTA_TEXTURE constant is used to select a texture color.

### -field D3DDDITSS_ALPHAARG2 

A D3DTA_TEXTURE that represents texture arguments. The D3DTA_TEXTURE constant is used to select a texture color.

### -field D3DDDITSS_BUMPENVMAT00 

A float that represents a bump mapping matrix.

### -field D3DDDITSS_BUMPENVMAT01 

A float that represents a bump mapping matrix.

### -field D3DDDITSS_BUMPENVMAT10 

A float that represents a bump mapping matrix.

### -field D3DDDITSS_BUMPENVMAT11 

A float that represents a bump mapping matrix.

### -field D3DDDITSS_TEXCOORDINDEX 

Identifies which set of texture coordinates index for this texture.

### -field D3DDDITSS_ADDRESSU 
### -field D3DDDITSS_ADDRESSV 
### -field D3DDDITSS_BORDERCOLOR 
### -field D3DDDITSS_MAGFILTER 
### -field D3DDDITSS_MINFILTER 
### -field D3DDDITSS_MIPFILTER 
### -field D3DDDITSS_MIPMAPLODBIAS 
### -field D3DDDITSS_MAXMIPLEVEL 
### -field D3DDDITSS_MAXANISOTROPY 
### -field D3DDDITSS_BUMPENVLSCALE 

A float scale for bump map luminance.

### -field D3DDDITSS_BUMPENVLOFFSET 

A float offset for bump map luminance.

### -field D3DDDITSS_TEXTURETRANSFORMFLAGS 

A [D3DTEXTURETRANSFORMFLAGS](../d3d9types/ne-d3d9types-_d3dtexturetransformflags.md) that controls texture transform.

### -field D3DDDITSS_ADDRESSW 
### -field D3DDDITSS_COLORARG0 

A third argument for triadic operations.

### -field D3DDDITSS_ALPHAARG0 

A third argument for triadic operations.

### -field D3DDDITSS_RESULTARG 

Arguments for the result, either D3DTA_CURRENT or D3DTA_TEMP.

D3DTA_TEMP is used to select a temporary register color.
D3DTA_CURRENT is used to select a stage destination register.

### -field D3DDDITSS_SRGBTEXTURE 
### -field D3DDDITSS_ELEMENTINDEX 
### -field D3DDDITSS_DMAPOFFSET 
### -field D3DDDITSS_CONSTANT 

A D3DTA_CONSTANT that indicates per-stage constant.

### -field D3DDDITSS_DISABLETEXTURECOLORKEY 

Disable texture color key.

### -field D3DDDITSS_TEXTURECOLORKEYVAL 

The texture color key value.

### -field D3DDDITSS_FORCE_DWORD 

Forces this enumeration to compile to 32 bits in size. 

## -remarks

## -see-also
