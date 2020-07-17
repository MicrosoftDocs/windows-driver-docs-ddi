---
UID: NS:d3d10umddi.D3D11_1_DDI_RASTERIZER_DESC
title: D3D11_1_DDI_RASTERIZER_DESC (d3d10umddi.h)
description: Describes a rasterizer state. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\d3d11_1_ddi_rasterizer_desc.htm
ms.assetid: a78655b3-3ca3-4632-9ac4-3efae6b10a0c
ms.date: 05/10/2018
keywords: ["D3D11_1_DDI_RASTERIZER_DESC structure"]
ms.keywords: D3D11_1_DDI_RASTERIZER_DESC, D3D11_1_DDI_RASTERIZER_DESC structure [Display Devices], d3d10umddi/D3D11_1_DDI_RASTERIZER_DESC, display.d3d11_1_ddi_rasterizer_desc
f1_keywords:
 - "d3d10umddi/D3D11_1_DDI_RASTERIZER_DESC"
 - "D3D11_1_DDI_RASTERIZER_DESC"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d10umddi.h
api_name:
- D3D11_1_DDI_RASTERIZER_DESC
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1_DDI_RASTERIZER_DESC
---

# D3D11_1_DDI_RASTERIZER_DESC structure


## -description


Describes a rasterizer state. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.


## -struct-fields




### -field FillMode

[in] A value that specifies the fill mode for primitives. This member must be set to one of the following values from the D3D10_DDI_FILL_MODE enumeration.

|Value|Meaning|
|--- |--- |
|D3D10_DDI_FILL_WIREFRAME (2)|Fills wireframes.|
|D3D10_DDI_FILL_SOLID (3)|Fills solids.|
 


### -field CullMode

[in] A value that specifies how back-facing triangles are culled, if at all. This member must be set to one of the following values from the D3D10_DDI_CULL_MODE enumeration.

|Value|Meaning|
|--- |--- |
|D3D10_DDI_CULL_NONE (1)|Do not cull any triangles.|
|D3D10_DDI_CULL_FRONT (2)|Cull front faces.|
|D3D10_DDI_CULL_BACK (3)|Cull back faces.|
 


### -field FrontCounterClockwise

[in] A Boolean value that specifies whether vertices that are provided in a counter-clockwise order (with respect to the rasterizer) are front facing. <b>TRUE</b> indicates they are; <b>FALSE</b> indicates that counter-clockwise vertices indicate back facing. 


### -field DepthBias

[in] A depth-bias constant to use in biasing formulas. For more information about <b>DepthBias</b>, see the Remarks section. 


### -field DepthBiasClamp

[in] A single-precision float vector that is used in biasing formulas. For more information about <b>DepthBiasClamp</b>, see the Remarks section. 


### -field SlopeScaledDepthBias

[in] A single-precision float vector that is used in biasing formulas. For more information about <b>SlopeScaledDepthBias</b>, see the Remarks section. 


### -field DepthClipEnable

[in] A Boolean value that specifies whether the driver should clip vertex z coordinates against the viewport depth range. <b>TRUE</b> indicates to clip; <b>FALSE</b> indicates not to clip. 


### -field ScissorEnable

[in] A Boolean value that specifies whether the driver should discard pixels that fall outside the appropriate scissor rectangular area. <b>TRUE</b> indicates to discard; <b>FALSE</b> indicates not to discard. 


### -field MultisampleEnable

[in] A Boolean value that specifies whether the driver must follow multiple-sampled rasterization rules. <b>TRUE</b> indicates to follow the rules; <b>FALSE</b> indicates following the rules is not required. Multiple-sampled rasterization rules hold true even if render targets contain only a single sample.  


### -field AntialiasedLineEnable

[in] A Boolean value that specifies whether the driver should render lines that follow the antialiased line rasterization rules. <b>TRUE</b> indicates to follow the rules; <b>FALSE</b> indicates following the rules is not required. The driver ignores the value in <b>AntialiasedLineEnable</b> if multiple-sampling rasterization rules are used instead. 


### -field ForcedSampleCount

[in] During rendering of unordered access views (UAVs) or rendering target views (RTVs), specifies whether to force a sample count, and if so, the maximum sample count. Valid values are 0, 1, 4, 8, and 16.

If zero, the driver should not force a sample count.


## -remarks



One of the artifacts with shadow buffer-based shadows is "shadow acne" (that is, a surface that shadows itself in an intermittent way because of inexactness in computing the depth of the surface from the shader that is compared against the depth of the same surface in the shadow buffer). One way to alleviate shadow acne is to use the <b>DepthBias</b> and <b>SlopeScaledDepthBias</b> members when you render a shadow buffer. The intent is to push surfaces out enough when rendering a shadow buffer. When those surfaces are compared against themselves through shader-computed z during the shadow test, the comparison result is consistent across the surface, and local-self-shadowing is avoided.

However, using <b>DepthBias</b> and <b>SlopeScaledDepthBias</b> alone can introduce a few artifacts. For example, an extremely steep polygon causes the bias equation to explode, which pushes the polygon extremely far away from the originating surface in the shadow map. Consider a steep face, with respect to a light, that is pushed away extremely far in relation to the dimensions of the parent object by depth biasing. Suppose this face is surrounded by shallower faces that the bias equation pushed out much less. The resulting shadow map has a huge discontinuity that can cause holes in the shadow that is cast by one surface onto another surface closer than the exploded faces. One way to help alleviate this particular problem is to use the <b>DepthBiasClamp</b> member, which provides an application-settable upper bound (positive or negative) on the magnitude of z biasing.



