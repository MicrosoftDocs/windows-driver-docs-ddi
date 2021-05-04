---
UID: NS:d3d10umddi.D3D10_DDI_RENDER_TARGET_BLEND_DESC1
title: D3D10_DDI_RENDER_TARGET_BLEND_DESC1 (d3d10umddi.h)
description: The D3D10_DDI_RENDER_TARGET_BLEND_DESC1 structure describes a blend state for a render target.
old-location: display\d3d10_ddi_render_target_blend_desc1.htm
ms.date: 04/01/2021
keywords: ["D3D10_DDI_RENDER_TARGET_BLEND_DESC1 structure"]
ms.keywords: D3D10_DDI_RENDER_TARGET_BLEND_DESC1, D3D10_DDI_RENDER_TARGET_BLEND_DESC1 structure [Display Devices], UMDisplayDriver_Dx10param_Structs_cc133adc-9ca8-4596-b3b8-9c3b352cd696.xml, d3d10umddi/D3D10_DDI_RENDER_TARGET_BLEND_DESC1, display.d3d10_ddi_render_target_blend_desc1
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D10_DDI_RENDER_TARGET_BLEND_DESC1 is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions.
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
req.typenames: D3D10_DDI_RENDER_TARGET_BLEND_DESC1
f1_keywords:
 - D3D10_DDI_RENDER_TARGET_BLEND_DESC1
 - d3d10umddi/D3D10_DDI_RENDER_TARGET_BLEND_DESC1
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D10_DDI_RENDER_TARGET_BLEND_DESC1
---

# D3D10_DDI_RENDER_TARGET_BLEND_DESC1 structure

## -description

The D3D10_DDI_RENDER_TARGET_BLEND_DESC1 structure describes a blend state for a render target.

## -struct-fields

### -field BlendEnable

[in] A Boolean value that specifies whether blending is enabled for the associated render target. **TRUE** indicates blending is enabled; **FALSE** indicates blending is disabled.

### -field SrcBlend

[in] A [**D3D10_DDI_BLEND**](ne-d3d10umddi-d3d10_ddi_blend.md)-typed value that indicates the blend mode of the source for the enabled render target.

### -field DestBlend

[in] A [**D3D10_DDI_BLEND**](ne-d3d10umddi-d3d10_ddi_blend.md)-typed value that indicates the blend mode of the destination for the enabled render target.

### -field BlendOp

[in] A [**D3D10_DDI_BLEND_OP**](ne-d3d10umddi-d3d10_ddi_blend_op.md)-typed value that indicates the blending operation for the enabled render target.

### -field SrcBlendAlpha

[in] A [**D3D10_DDI_BLEND**](ne-d3d10umddi-d3d10_ddi_blend.md)-typed value that indicates the transparency blend mode of the source for the enabled render target.

### -field DestBlendAlpha

[in] A [**D3D10_DDI_BLEND**](ne-d3d10umddi-d3d10_ddi_blend.md)-typed value that indicates the transparency blend mode of the destination for the enabled render target.

### -field BlendOpAlpha

[in] A [**D3D10_DDI_BLEND_OP**](ne-d3d10umddi-d3d10_ddi_blend_op.md)-typed value that indicates the transparency blending operation for the enabled render target.

### -field RenderTargetWriteMask

[in] An 8-bit bitwise value that indicates the write properties for the enabled render target. Each bit must be set to one of the following values from the D3D10_DDI_COLOR_WRITE_ENABLE enumeration.

|Value|Meaning|
|--- |--- |
|D3D10_DDI_COLOR_WRITE_ENABLE_RED (1)   |Writes red|
|D3D10_DDI_COLOR_WRITE_ENABLE_GREEN (2) |Writes green|
|D3D10_DDI_COLOR_WRITE_ENABLE_BLUE (4)  |Writes blue|
|D3D10_DDI_COLOR_WRITE_ENABLE_ALPHA (8) |Writes a transparency level|
|D3D10_DDI_COLOR_WRITE_ENABLE_ALL (bitwise OR of 1,2,4,8) |Writes red, green, blue, and a transparency level|

## -remarks

An array of D3D10_DDI_RENDER_TARGET_BLEND_DESC1 structures are specified in the **RenderTarget** member of the [**D3D10_1_DDI_BLEND_DESC**](ns-d3d10umddi-d3d10_1_ddi_blend_desc.md) structure to describe a blend state.

## -see-also

[**CalcPrivateBlendStateSize**](nc-d3d10umddi-pfnd3d10ddi_calcprivateblendstatesize.md)

[**CreateBlendState(D3D10_1)**](nc-d3d10umddi-pfnd3d10_1ddi_createblendstate.md)

[**D3D10_1_DDI_BLEND_DESC**](ns-d3d10umddi-d3d10_1_ddi_blend_desc.md)

[**D3D10_DDI_BLEND**](ne-d3d10umddi-d3d10_ddi_blend.md)

[**D3D10_DDI_BLEND_OP**](ne-d3d10umddi-d3d10_ddi_blend_op.md)
