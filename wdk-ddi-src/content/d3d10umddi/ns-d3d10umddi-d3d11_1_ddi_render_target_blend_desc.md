---
UID: NS:d3d10umddi.D3D11_1_DDI_RENDER_TARGET_BLEND_DESC
title: D3D11_1_DDI_RENDER_TARGET_BLEND_DESC
author: windows-driver-content
description: Describes a blend state for a render target. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\d3d11_1_ddi_render_target_blend_desc.htm
old-project: display
ms.assetid: ad90ad4c-625f-4177-8160-cd6576942c91
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11_1_DDI_RENDER_TARGET_BLEND_DESC, d3d10umddi/D3D11_1_DDI_RENDER_TARGET_BLEND_DESC, display.d3d11_1_ddi_render_target_blend_desc, D3D11_1_DDI_RENDER_TARGET_BLEND_DESC structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	D3d10umddi.h
apiname: 
-	D3D11_1_DDI_RENDER_TARGET_BLEND_DESC
product: Windows
targetos: Windows
req.typenames: D3D11_1_DDI_RENDER_TARGET_BLEND_DESC
---

# D3D11_1_DDI_RENDER_TARGET_BLEND_DESC structure


## -description


Describes a blend state for a render target. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.


## -syntax


````
typedef struct D3D11_1_DDI_RENDER_TARGET_BLEND_DESC {
  BOOL                 BlendEnable;
  BOOL                 LogicOpEnable;
  D3D10_DDI_BLEND      SrcBlend;
  D3D10_DDI_BLEND      DestBlend;
  D3D10_DDI_BLEND_OP   BlendOp;
  D3D10_DDI_BLEND      SrcBlendAlpha;
  D3D10_DDI_BLEND      DestBlendAlpha;
  D3D10_DDI_BLEND_OP   BlendOpAlpha;
  D3D11_1_DDI_LOGIC_OP LogicOp;
  UINT8                RenderTargetWriteMask;
} D3D11_1_DDI_RENDER_TARGET_BLEND_DESC;
````


## -struct-fields




### -field BlendEnable

[in] A Boolean value that specifies whether blending is enabled for the associated render target. <b>TRUE</b> indicates blending is enabled; <b>FALSE</b> indicates blending is disabled.
<div class="alert"><b>Note</b>  The <b>LogicOpEnable</b> and <b>BlendEnable</b> members must not both be <b>TRUE</b>.</div><div> </div>

### -field LogicOpEnable

Specifies whether shader logic operations given by the <b>LogicOp</b> member are available in the blend state. The user-mode display driver sets <b>LogicOpEnable</b> to <b>TRUE</b> if logic operations are available in the blend state and <b>FALSE</b> otherwise. 

This member is <b>FALSE</b> if the   driver supports Direct3D feature level 9.1, 9.2, and 9.3. This member is optional if the driver supports feature level 10, 10.1, and 11.

This member is <b>TRUE</b> if the driver supports feature level 11.1 and later.
<div class="alert"><b>Note</b>  The <b>LogicOpEnable</b> and <b>BlendEnable</b> members must not both be <b>TRUE</b>.</div><div> </div>

### -field SrcBlend

[in] A value of type <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend.md">D3D10_DDI_BLEND</a> that indicates the blend mode of the source for the enabled render target. 


### -field DestBlend

[in] A value of type <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend.md">D3D10_DDI_BLEND</a> that indicates the blend mode of the destination for the enabled render target. 


### -field BlendOp

[in] A value of type <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend_op.md">D3D10_DDI_BLEND_OP</a> that indicates the blending operation for the enabled render target. 


### -field SrcBlendAlpha

[in] A value of type <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend.md">D3D10_DDI_BLEND</a> that indicates the transparency blend mode of the source for the enabled render target. 


### -field DestBlendAlpha

[in] A value of type <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend.md">D3D10_DDI_BLEND</a> that indicates the transparency blend mode of the destination for the enabled render target. 


### -field BlendOpAlpha

[in] A value of type <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend_op.md">D3D10_DDI_BLEND_OP</a> that indicates the transparency blending operation for the enabled render target. 


### -field LogicOp

[in] A value of type <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1_ddi_logic_op.md">D3D11_1_DDI_LOGIC_OP</a> that specifies  shader logic operations that are available in the blend state.


### -field RenderTargetWriteMask

[in] An 8-bit bitwise value that indicates the write properties for the enabled render target. Each bit must be set to one of the following values from the D3D10_DDI_COLOR_WRITE_ENABLE enumeration.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>D3D10_DDI_COLOR_WRITE_ENABLE_RED</b> (1)

</td>
<td>
Writes red

</td>
</tr>
<tr>
<td>
<b>D3D10_DDI_COLOR_WRITE_ENABLE_GREEN</b> (2)

</td>
<td>
Writes green

</td>
</tr>
<tr>
<td>
<b>D3D10_DDI_COLOR_WRITE_ENABLE_BLUE</b> (4)

</td>
<td>
Writes blue

</td>
</tr>
<tr>
<td>
<b>D3D10_DDI_COLOR_WRITE_ENABLE_ALPHA</b> (8)

</td>
<td>
Writes a transparency level

</td>
</tr>
<tr>
<td>
<b>D3D10_DDI_COLOR_WRITE_ENABLE_ALL</b> (1 | 2 | 4 | 8)

</td>
<td>
Writes red, green, blue, and a transparency level

</td>
</tr>
</table> 


## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1_ddi_blend_desc.md">D3D11_1_DDI_BLEND_DESC</a>

<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend.md">D3D10_DDI_BLEND</a>

<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1_ddi_logic_op.md">D3D11_1_DDI_LOGIC_OP</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivateblendstatesize.md">CalcPrivateBlendStateSize(D3D11_1)</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createblendstate.md">CreateBlendState(D3D11_1)</a>

<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend_op.md">D3D10_DDI_BLEND_OP</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1_DDI_RENDER_TARGET_BLEND_DESC structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

