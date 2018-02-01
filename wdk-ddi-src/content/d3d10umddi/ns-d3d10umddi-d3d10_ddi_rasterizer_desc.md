---
UID: NS:d3d10umddi.D3D10_DDI_RASTERIZER_DESC
title: D3D10_DDI_RASTERIZER_DESC
author: windows-driver-content
description: The D3D10_DDI_RASTERIZER_DESC structure describes a rasterizer state.
old-location: display\d3d10_ddi_rasterizer_desc.htm
old-project: display
ms.assetid: d4247ec7-1995-45cf-83e3-958acbfd7915
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D10_DDI_RASTERIZER_DESC structure [Display Devices], D3D10_DDI_RASTERIZER_DESC, UMDisplayDriver_Dx10param_Structs_bf0538cd-a9de-44f6-a028-d147b77324fc.xml, display.d3d10_ddi_rasterizer_desc, d3d10umddi/D3D10_DDI_RASTERIZER_DESC
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3D10_DDI_RASTERIZER_DESC
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_RASTERIZER_DESC
---

# D3D10_DDI_RASTERIZER_DESC structure


## -description


The D3D10_DDI_RASTERIZER_DESC structure describes a rasterizer state.


## -syntax


````
typedef struct D3D10_DDI_RASTERIZER_DESC {
  D3D10_DDI_FILL_MODE FillMode;
  D3D10_DDI_CULL_MODE CullMode;
  BOOL                FrontCounterClockwise;
  INT32               DepthBias;
  FLOAT               DepthBiasClamp;
  FLOAT               SlopeScaledDepthBias;
  BOOL                DepthClipEnable;
  BOOL                ScissorEnable;
  BOOL                MultisampleEnable;
  BOOL                AntialiasedLineEnable;
} D3D10_DDI_RASTERIZER_DESC;
````


## -struct-fields




### -field FillMode

[in] A value that specifies the fill mode for primitives. This member must be set to one of the following values from the D3D10_DDI_FILL_MODE enumeration.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3D10_DDI_FILL_WIREFRAME (2)

</td>
<td>
Fills wireframes.

</td>
</tr>
<tr>
<td>
D3D10_DDI_FILL_SOLID (3)

</td>
<td>
Fills solids.

</td>
</tr>
</table> 


### -field CullMode

[in] A value that specifies how back-facing triangles are culled, if at all. This member must be set to one of the following values from the D3D10_DDI_CULL_MODE enumeration.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3D10_DDI_CULL_NONE (1)

</td>
<td>
Do not cull any triangles.

</td>
</tr>
<tr>
<td>
D3D10_DDI_CULL_FRONT (2)

</td>
<td>
Cull front faces.

</td>
</tr>
<tr>
<td>
D3D10_DDI_CULL_BACK (3)

</td>
<td>
Cull back faces.

</td>
</tr>
</table> 


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

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivaterasterizerstatesize.md">CalcPrivateRasterizerStateSize</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createrasterizerstate.md">CreateRasterizerState</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_RASTERIZER_DESC structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

