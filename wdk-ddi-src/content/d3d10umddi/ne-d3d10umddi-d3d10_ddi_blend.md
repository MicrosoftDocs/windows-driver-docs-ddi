---
UID: NE:d3d10umddi.D3D10_DDI_BLEND
title: D3D10_DDI_BLEND (d3d10umddi.h)
description: The D3D10_DDI_BLEND enumeration type contains values that identify blend modes in a call to the driver's CreateBlendState function.
old-location: display\d3d10_ddi_blend.htm
ms.date: 08/22/2022
keywords: ["D3D10_DDI_BLEND enumeration"]
ms.keywords: D3D10_DDI_BLEND, D3D10_DDI_BLEND enumeration [Display Devices], D3D10_DDI_BLEND_BLEND_FACTOR, D3D10_DDI_BLEND_DEST_ALPHA, D3D10_DDI_BLEND_DEST_COLOR, D3D10_DDI_BLEND_INVBLEND_FACTOR, D3D10_DDI_BLEND_INV_DEST_ALPHA, D3D10_DDI_BLEND_INV_DEST_COLOR, D3D10_DDI_BLEND_INV_SRC1_ALPHA, D3D10_DDI_BLEND_INV_SRC1_COLOR, D3D10_DDI_BLEND_INV_SRC_ALPHA, D3D10_DDI_BLEND_INV_SRC_COLOR, D3D10_DDI_BLEND_ONE, D3D10_DDI_BLEND_SRC1_ALPHA, D3D10_DDI_BLEND_SRC1_COLOR, D3D10_DDI_BLEND_SRC_ALPHA, D3D10_DDI_BLEND_SRC_ALPHASAT, D3D10_DDI_BLEND_SRC_COLOR, D3D10_DDI_BLEND_ZERO, UMDisplayDriver_Dx10param_Structs_de092af6-e6a8-4772-af32-b92d2afcea79.xml, d3d10umddi/D3D10_DDI_BLEND, d3d10umddi/D3D10_DDI_BLEND_BLEND_FACTOR, d3d10umddi/D3D10_DDI_BLEND_DEST_ALPHA, d3d10umddi/D3D10_DDI_BLEND_DEST_COLOR, d3d10umddi/D3D10_DDI_BLEND_INVBLEND_FACTOR, d3d10umddi/D3D10_DDI_BLEND_INV_DEST_ALPHA, d3d10umddi/D3D10_DDI_BLEND_INV_DEST_COLOR, d3d10umddi/D3D10_DDI_BLEND_INV_SRC1_ALPHA, d3d10umddi/D3D10_DDI_BLEND_INV_SRC1_COLOR, d3d10umddi/D3D10_DDI_BLEND_INV_SRC_ALPHA, d3d10umddi/D3D10_DDI_BLEND_INV_SRC_COLOR, d3d10umddi/D3D10_DDI_BLEND_ONE, d3d10umddi/D3D10_DDI_BLEND_SRC1_ALPHA, d3d10umddi/D3D10_DDI_BLEND_SRC1_COLOR, d3d10umddi/D3D10_DDI_BLEND_SRC_ALPHA, d3d10umddi/D3D10_DDI_BLEND_SRC_ALPHASAT, d3d10umddi/D3D10_DDI_BLEND_SRC_COLOR, d3d10umddi/D3D10_DDI_BLEND_ZERO, display.d3d10_ddi_blend
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.typenames: D3D10_DDI_BLEND
f1_keywords:
 - D3D10_DDI_BLEND
 - d3d10umddi/D3D10_DDI_BLEND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D10_DDI_BLEND
---

# D3D10_DDI_BLEND enumeration

## -description

The D3D10_DDI_BLEND enumeration type contains values that identify blend modes in a call to the driver's [**CreateBlendState**](nc-d3d10umddi-pfnd3d10ddi_createblendstate.md) function.

## -enum-fields

### -field D3D10_DDI_BLEND_ZERO:1

Blend factor is (0, 0, 0, 0).

### -field D3D10_DDI_BLEND_ONE:2

Blend factor is (1, 1, 1, 1).

### -field D3D10_DDI_BLEND_SRC_COLOR:3

Blend factor is (Rₛ,Gₛ,Bₛ,Aₛ).

### -field D3D10_DDI_BLEND_INV_SRC_COLOR:4

Blend factor is (1 - Rₛ, 1 - Gₛ, 1 - Bₛ, 1 - Aₛ).

### -field D3D10_DDI_BLEND_SRC_ALPHA:5

Blend factor is (Aₛ, Aₛ, Aₛ, Aₛ).

### -field D3D10_DDI_BLEND_INV_SRC_ALPHA:6

Blend factor is ( 1 - Aₛ, 1 - Aₛ, 1 - Aₛ, 1 - Aₛ).

### -field D3D10_DDI_BLEND_DEST_ALPHA:7

Blend factor is (A<sub>d</sub>, A<sub>d</sub>, A<sub>d</sub>, A<sub>d</sub>) of the current render target that is being blended.

### -field D3D10_DDI_BLEND_INV_DEST_ALPHA:8

Blend factor is (1 - A<sub>d</sub>, 1 - A<sub>d</sub>, 1 - A<sub>d</sub>, 1 - A<sub>d</sub>) of the current render target that is being blended.

### -field D3D10_DDI_BLEND_DEST_COLOR:9

Blend factor is (R<sub>d</sub>, G<sub>d</sub>, B<sub>d</sub>, A<sub>d</sub>) of the current render target that is being blended.

### -field D3D10_DDI_BLEND_INV_DEST_COLOR:10

Blend factor is (1 - R<sub>d</sub>, 1 - G<sub>d</sub>, 1 - B<sub>d</sub>, 1 - A<sub>d</sub>) of the current render target that is being blended.

### -field D3D10_DDI_BLEND_SRC_ALPHASAT:11

Blend factor is (f, f, f, 1); f = min(A, 1 - A<sub>d</sub>).

### -field D3D10_DDI_BLEND_BLEND_FACTOR:14

Constant color-blending factor that the frame-buffer blender uses.

### -field D3D10_DDI_BLEND_INVBLEND_FACTOR:15

Inverted constant color-blending factor that the frame-buffer blender uses.

### -field D3D10_DDI_BLEND_SRC1_COLOR:16

Blend factor is the red, green, and blue (RGB) components of a pixel shader output register (PS output o1.rgb).

### -field D3D10_DDI_BLEND_INV_SRC1_COLOR:17

Blend factor is the inversion of the RGB components of a pixel shader output register (1.0f - PS output o1.rgb).

### -field D3D10_DDI_BLEND_SRC1_ALPHA:18

Blend factor is the alpha component of a pixel shader output register (PS output o1.a).

### -field D3D10_DDI_BLEND_INV_SRC1_ALPHA:19

Blend factor is the inversion of the alpha component of a pixel shader output register (1.0f - PS output o1.a).

### -field D3D10_DDI_BLEND_ALPHA_FACTOR:20

Blend factor is the alpha component of the color-blending factor that the frame-buffer blender uses.

### -field D3D10_DDI_BLEND_INVALPHA_FACTOR:21

Blend factor is 1 minus the alpha component of the color-blending factor that the frame-buffer blender uses.

## -remarks

A *blend mode* is an algorithm that is used to determine how a texture is blended with the colors of the surface that the texture is applied to. A *blend factor* is a description of how each color component is blended in texture blending.

## -see-also

[**CreateBlendState**](nc-d3d10umddi-pfnd3d10ddi_createblendstate.md)
