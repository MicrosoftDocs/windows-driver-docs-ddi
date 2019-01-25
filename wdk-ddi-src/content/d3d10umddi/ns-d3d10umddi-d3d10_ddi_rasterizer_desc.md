---
UID: NS:d3d10umddi.D3D10_DDI_RASTERIZER_DESC
title: D3D10_DDI_RASTERIZER_DESC (d3d10umddi.h)
description: The D3D10_DDI_RASTERIZER_DESC structure describes a rasterizer state.
old-location: display\d3d10_ddi_rasterizer_desc.htm
ms.assetid: d4247ec7-1995-45cf-83e3-958acbfd7915
ms.date: 05/10/2018
ms.keywords: D3D10_DDI_RASTERIZER_DESC, D3D10_DDI_RASTERIZER_DESC structure [Display Devices], UMDisplayDriver_Dx10param_Structs_bf0538cd-a9de-44f6-a028-d147b77324fc.xml, d3d10umddi/D3D10_DDI_RASTERIZER_DESC, display.d3d10_ddi_rasterizer_desc
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D10_DDI_RASTERIZER_DESC
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10_DDI_RASTERIZER_DESC
---

# D3D10_DDI_RASTERIZER_DESC structure


## -description


The D3D10_DDI_RASTERIZER_DESC structure describes a rasterizer state.


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

[in] A depth-bias constant to use in biasing formulas. For more information about <b>DepthBias</b>, see the following Remarks section. 


### -field DepthBiasClamp

[in] A single-precision float vector that is used in biasing formulas. For more information about <b>DepthBiasClamp</b>, see the following Remarks section. 


### -field SlopeScaledDepthBias

[in] A single-precision float vector that is used in biasing formulas. For more information about <b>SlopeScaledDepthBias</b>, see the following Remarks section. 


### -field DepthClipEnable

[in] A Boolean value that specifies whether the driver should clip vertex z coordinates against the viewport depth range. <b>TRUE</b> indicates to clip; <b>FALSE</b> indicates not to clip. 


### -field ScissorEnable

[in] A Boolean value that specifies whether the driver should discard pixels that fall outside the appropriate scissor rectangular area. <b>TRUE</b> indicates to discard; <b>FALSE</b> indicates not to discard. 


### -field MultisampleEnable

[in] A Boolean value that specifies whether the driver must follow multiple-sampled rasterization rules. <b>TRUE</b> indicates to follow the rules; <b>FALSE</b> indicates following the rules is not required. Multiple-sampled rasterization rules hold true even if render targets contain only a single sample.  


### -field AntialiasedLineEnable

[in] A Boolean value that specifies whether the driver should render lines that follow the antialiased line rasterization rules. <b>TRUE</b> indicates to follow the rules; <b>FALSE</b> indicates following the rules is not required. The driver ignores the value in <b>AntialiasedLineEnable</b> if multiple-sampling rasterization rules are used instead. 


## -remarks



One of the artifacts with shadow buffer-based shadows is "shadow acne" (that is, a surface that shadows itself in an intermittent way because of inexactness in computing the depth of the surface from the shader that is compared against the depth of the same surface in the shadow buffer). One way to alleviate shadow acne is to use the <b>DepthBias</b> and <b>SlopeScaledDepthBias</b> members when you render a shadow buffer. The intent is to push surfaces out enough when rendering a shadow buffer. When those surfaces are compared against themselves through shader-computed z during the shadow test, the comparison result is consistent across the surface, and local-self-shadowing is avoided.

However, using <b>DepthBias</b> and <b>SlopeScaledDepthBias</b> alone can introduce a few artifacts. For example, an extremely steep polygon causes the bias equation to explode, which pushes the polygon extremely far away from the originating surface in the shadow map. Consider a steep face, with respect to a light, that is pushed away extremely far in relation to the dimensions of the parent object by depth biasing. Suppose this face is surrounded by shallower faces that the bias equation pushed out much less. The resulting shadow map has a huge discontinuity that can cause holes in the shadow that is cast by one surface onto another surface closer than the exploded faces. One way to help alleviate this particular problem is to use the <b>DepthBiasClamp</b> member, which provides an application-settable upper bound (positive or negative) on the magnitude of z biasing.




## -see-also




<a href="https://msdn.microsoft.com/8b10b2b8-21b0-451c-9a85-353222d9c288">CalcPrivateRasterizerStateSize</a>



<a href="https://msdn.microsoft.com/4507b92e-2437-4f90-b527-e06773ca1e08">CreateRasterizerState</a>
 

 

