---
UID: NS:d3d10umddi.D3D10_DDI_RENDER_TARGET_BLEND_DESC1
title: D3D10_DDI_RENDER_TARGET_BLEND_DESC1
author: windows-driver-content
description: The D3D10_DDI_RENDER_TARGET_BLEND_DESC1 structure describes a blend state for a render target.
old-location: display\d3d10_ddi_render_target_blend_desc1.htm
old-project: display
ms.assetid: 4cbc3072-46f1-40c3-ba3f-4d99f19b280e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3d10_ddi_render_target_blend_desc1, UMDisplayDriver_Dx10param_Structs_cc133adc-9ca8-4596-b3b8-9c3b352cd696.xml, D3D10_DDI_RENDER_TARGET_BLEND_DESC1 structure [Display Devices], d3d10umddi/D3D10_DDI_RENDER_TARGET_BLEND_DESC1, D3D10_DDI_RENDER_TARGET_BLEND_DESC1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	d3d10umddi.h
apiname: 
-	D3D10_DDI_RENDER_TARGET_BLEND_DESC1
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_RENDER_TARGET_BLEND_DESC1
---

# D3D10_DDI_RENDER_TARGET_BLEND_DESC1 structure


## -description


The D3D10_DDI_RENDER_TARGET_BLEND_DESC1 structure describes a blend state for a render target.


## -syntax


````
typedef struct D3D10_DDI_RENDER_TARGET_BLEND_DESC1 {
  BOOL               BlendEnable;
  D3D10_DDI_BLEND    SrcBlend;
  D3D10_DDI_BLEND    DestBlend;
  D3D10_DDI_BLEND_OP BlendOp;
  D3D10_DDI_BLEND    SrcBlendAlpha;
  D3D10_DDI_BLEND    DestBlendAlpha;
  D3D10_DDI_BLEND_OP BlendOpAlpha;
  UINT8              RenderTargetWriteMask;
} D3D10_DDI_RENDER_TARGET_BLEND_DESC1;
````


## -struct-fields




### -field BlendEnable

[in] A Boolean value that specifies whether blending is enabled for the associated render target. <b>TRUE</b> indicates blending is enabled; <b>FALSE</b> indicates blending is disabled. 


### -field SrcBlend

[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend.md">D3D10_DDI_BLEND</a>-typed value that indicates the blend mode of the source for the enabled render target. 


### -field DestBlend

[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend.md">D3D10_DDI_BLEND</a>-typed value that indicates the blend mode of the destination for the enabled render target. 


### -field BlendOp

[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend_op.md">D3D10_DDI_BLEND_OP</a>-typed value that indicates the blending operation for the enabled render target. 


### -field SrcBlendAlpha

[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend.md">D3D10_DDI_BLEND</a>-typed value that indicates the transparency blend mode of the source for the enabled render target. 


### -field DestBlendAlpha

[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend.md">D3D10_DDI_BLEND</a>-typed value that indicates the transparency blend mode of the destination for the enabled render target. 


### -field BlendOpAlpha

[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend_op.md">D3D10_DDI_BLEND_OP</a>-typed value that indicates the transparency blending operation for the enabled render target. 


### -field RenderTargetWriteMask

[in] An 8-bit bitwise value that indicates the write properties for the enabled render target. Each bit must be set to one of the following values from the D3D10_DDI_COLOR_WRITE_ENABLE enumeration.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3D10_DDI_COLOR_WRITE_ENABLE_RED (1)

</td>
<td>
Writes red

</td>
</tr>
<tr>
<td>
D3D10_DDI_COLOR_WRITE_ENABLE_GREEN (2)

</td>
<td>
Writes green

</td>
</tr>
<tr>
<td>
D3D10_DDI_COLOR_WRITE_ENABLE_BLUE (4)

</td>
<td>
Writes blue

</td>
</tr>
<tr>
<td>
D3D10_DDI_COLOR_WRITE_ENABLE_ALPHA (8)

</td>
<td>
Writes a transparency level

</td>
</tr>
<tr>
<td>
D3D10_DDI_COLOR_WRITE_ENABLE_ALL (1 | 2 | 4 | 8)

</td>
<td>
Writes red, green, blue, and a transparency level

</td>
</tr>
</table> 


## -remarks


An array of D3D10_DDI_RENDER_TARGET_BLEND_DESC1 structures are specified in the <b>RenderTarget</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10_1_ddi_blend_desc.md">D3D10_1_DDI_BLEND_DESC</a> structure to describe a blend state. 



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_1ddi_calcprivateblendstatesize.md">CalcPrivateBlendStateSize(D3D10_1)</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_1_ddi_blend_desc.md">D3D10_1_DDI_BLEND_DESC</a>

<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend.md">D3D10_DDI_BLEND</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_1ddi_createblendstate.md">CreateBlendState(D3D10_1)</a>

<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend_op.md">D3D10_DDI_BLEND_OP</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_RENDER_TARGET_BLEND_DESC1 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

