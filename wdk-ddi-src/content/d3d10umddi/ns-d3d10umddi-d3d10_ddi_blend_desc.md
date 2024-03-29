---
UID: NS:d3d10umddi.D3D10_DDI_BLEND_DESC
title: D3D10_DDI_BLEND_DESC (d3d10umddi.h)
description: The D3D10_DDI_BLEND_DESC structure describes a blend state.
old-location: display\d3d10_ddi_blend_desc.htm
ms.date: 04/01/2021
keywords: ["D3D10_DDI_BLEND_DESC structure"]
ms.keywords: D3D10_DDI_BLEND_DESC, D3D10_DDI_BLEND_DESC structure [Display Devices], UMDisplayDriver_Dx10param_Structs_8dd04d52-105b-4cc3-be87-5900625dcd6d.xml, d3d10umddi/D3D10_DDI_BLEND_DESC, display.d3d10_ddi_blend_desc
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
targetos: Windows
tech.root: display
req.typenames: D3D10_DDI_BLEND_DESC
f1_keywords:
 - D3D10_DDI_BLEND_DESC
 - d3d10umddi/D3D10_DDI_BLEND_DESC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D10_DDI_BLEND_DESC
---

# D3D10_DDI_BLEND_DESC structure

## -description

The **D3D10_DDI_BLEND_DESC** structure describes a blend state.

## -struct-fields

### -field AlphaToCoverageEnable [in]

A Boolean value that specifies whether transparency coverage is enabled. **TRUE** indicates transparency coverage is enabled; **FALSE** indicates transparency coverage is disabled. This member is relevant for multiple-sample antialiasing only.

### -field BlendEnable [in]

An array of Boolean values that specify whether blending is enabled for each associated render target. **TRUE** indicates blending is enabled; **FALSE** indicates blending is disabled.

### -field SrcBlend [in]

A [**D3D10_DDI_BLEND**](ne-d3d10umddi-d3d10_ddi_blend.md)-typed value that indicates the blend mode of the source for all enabled render targets.

### -field DestBlend [in]

A [**D3D10_DDI_BLEND**](ne-d3d10umddi-d3d10_ddi_blend.md)-typed value that indicates the blend mode of the destination for all enabled render targets.

### -field BlendOp [in]

A [**D3D10_DDI_BLEND_OP**](ne-d3d10umddi-d3d10_ddi_blend_op.md)-typed value that indicates the blending operation for all enabled render targets.

### -field SrcBlendAlpha [in]

A [**D3D10_DDI_BLEND**](ne-d3d10umddi-d3d10_ddi_blend.md)-typed value that indicates the transparency blend mode of the source for all enabled render targets.

### -field DestBlendAlpha [in]

A [**D3D10_DDI_BLEND**](ne-d3d10umddi-d3d10_ddi_blend.md)-typed value that indicates the transparency blend mode of the destination for all enabled render targets.

### -field BlendOpAlpha [in]

A [**D3D10_DDI_BLEND_OP**](ne-d3d10umddi-d3d10_ddi_blend_op.md)-typed value that indicates the transparency blending operation for all enabled render targets.

### -field RenderTargetWriteMask [in]

An array of 8-bit bitwise values that indicate the write properties for each associated render target. Each bit of each element must be set to one of the following values from the D3D10_DDI_COLOR_WRITE_ENABLE enumeration.

|Value|Meaning|
|--- |--- |
|D3D10_DDI_COLOR_WRITE_ENABLE_RED (1)   |Writes red|
|D3D10_DDI_COLOR_WRITE_ENABLE_GREEN (2) |Writes green|
|D3D10_DDI_COLOR_WRITE_ENABLE_BLUE (4)  |Writes blue|
|D3D10_DDI_COLOR_WRITE_ENABLE_ALPHA (8) |Writes a transparency level|
|D3D10_DDI_COLOR_WRITE_ENABLE_ALL (bitwise OR of 1,2,4,8)|Writes red, green, blue, and a transparency level|

## -see-also

[**CalcPrivateBlendStateSize**](nc-d3d10umddi-pfnd3d10ddi_calcprivateblendstatesize.md)

[**CreateBlendState**](nc-d3d10umddi-pfnd3d10ddi_createblendstate.md)

[**D3D10_DDI_BLEND**](ne-d3d10umddi-d3d10_ddi_blend.md)

[**D3D10_DDI_BLEND_OP**](ne-d3d10umddi-d3d10_ddi_blend_op.md)
