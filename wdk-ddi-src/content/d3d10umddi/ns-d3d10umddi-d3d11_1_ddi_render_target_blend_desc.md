---
UID: NS:d3d10umddi.D3D11_1_DDI_RENDER_TARGET_BLEND_DESC
title: D3D11_1_DDI_RENDER_TARGET_BLEND_DESC (d3d10umddi.h)
description: Describes a blend state for a render target. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\d3d11_1_ddi_render_target_blend_desc.htm
ms.date: 05/10/2018
keywords: ["D3D11_1_DDI_RENDER_TARGET_BLEND_DESC structure"]
ms.keywords: D3D11_1_DDI_RENDER_TARGET_BLEND_DESC, D3D11_1_DDI_RENDER_TARGET_BLEND_DESC structure [Display Devices], d3d10umddi/D3D11_1_DDI_RENDER_TARGET_BLEND_DESC, display.d3d11_1_ddi_render_target_blend_desc
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.typenames: D3D11_1_DDI_RENDER_TARGET_BLEND_DESC
f1_keywords:
 - D3D11_1_DDI_RENDER_TARGET_BLEND_DESC
 - d3d10umddi/D3D11_1_DDI_RENDER_TARGET_BLEND_DESC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3D11_1_DDI_RENDER_TARGET_BLEND_DESC
---

# D3D11_1_DDI_RENDER_TARGET_BLEND_DESC structure

## -description

Describes a blend state for a render target. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.

## -struct-fields

### -field BlendEnable

[in] A Boolean value that specifies whether blending is enabled for the associated render target. **TRUE** indicates blending is enabled; **FALSE** indicates blending is disabled.

> [!NOTE]
> The **LogicOpEnable** and **BlendEnable** members must not both be **TRUE**.

### -field LogicOpEnable

Specifies whether shader logic operations given by the **LogicOp** member are available in the blend state. The user-mode display driver sets **LogicOpEnable** to **TRUE** if logic operations are available in the blend state and **FALSE** otherwise.

This member is **FALSE** if the driver supports Direct3D feature level 9.1, 9.2, and 9.3. This member is optional if the driver supports feature level 10, 10.1, and 11.

This member is **TRUE** if the driver supports feature level 11.1 and later.

> [!NOTE]
> The **LogicOpEnable** and **BlendEnable** members must not both be **TRUE**.

### -field SrcBlend

[in] A value of type [**D3D10_DDI_BLEND**](ne-d3d10umddi-d3d10_ddi_blend.md) that indicates the blend mode of the source for the enabled render target.

### -field DestBlend

[in] A value of type [**D3D10_DDI_BLEND**](ne-d3d10umddi-d3d10_ddi_blend.md) that indicates the blend mode of the destination for the enabled render target.

### -field BlendOp

[in] A value of type [**D3D10_DDI_BLEND_OP**](ne-d3d10umddi-d3d10_ddi_blend_op.md) that indicates the blending operation for the enabled render target.

### -field SrcBlendAlpha

[in] A value of type [**D3D10_DDI_BLEND**](ne-d3d10umddi-d3d10_ddi_blend.md) that indicates the transparency blend mode of the source for the enabled render target.

### -field DestBlendAlpha

[in] A value of type [**D3D10_DDI_BLEND**](ne-d3d10umddi-d3d10_ddi_blend.md) that indicates the transparency blend mode of the destination for the enabled render target.

### -field BlendOpAlpha

[in] A value of type [**D3D10_DDI_BLEND_OP**](ne-d3d10umddi-d3d10_ddi_blend_op.md) that indicates the transparency blending operation for the enabled render target.

### -field LogicOp

[in] A value of type [**D3D11_1_DDI_LOGIC_OP**](ne-d3d10umddi-d3d11_1_ddi_logic_op.md) that specifies shader logic operations that are available in the blend state.

### -field RenderTargetWriteMask

[in] An 8-bit bitwise value that indicates the write properties for the enabled render target. Each bit must be set to one of the following values from the D3D10_DDI_COLOR_WRITE_ENABLE enumeration.

|Value|Meaning|
|--- |--- |
|D3D10_DDI_COLOR_WRITE_ENABLE_RED (1)   |Writes red|
|D3D10_DDI_COLOR_WRITE_ENABLE_GREEN (2) |Writes green|
|D3D10_DDI_COLOR_WRITE_ENABLE_BLUE (4)  |Writes blue|
|D3D10_DDI_COLOR_WRITE_ENABLE_ALPHA (8) |Writes a transparency level|
|D3D10_DDI_COLOR_WRITE_ENABLE_ALL (bitwise OR of 1,2,4,8)|Writes red, green, blue, and a transparency level|

## -see-also

[**CalcPrivateBlendStateSize**](nc-d3d10umddi-pfnd3d10ddi_calcprivateblendstatesize.md)

[**CreateBlendState(D3D11_1)**](nc-d3d10umddi-pfnd3d11_1ddi_createblendstate.md)

[**D3D10_DDI_BLEND**](ne-d3d10umddi-d3d10_ddi_blend.md)

[**D3D10_DDI_BLEND_OP**](ne-d3d10umddi-d3d10_ddi_blend_op.md)

[**D3D11_1_DDI_BLEND_DESC**](ns-d3d10umddi-d3d11_1_ddi_blend_desc.md)

[**D3D11_1_DDI_LOGIC_OP**](ne-d3d10umddi-d3d11_1_ddi_logic_op.md)
