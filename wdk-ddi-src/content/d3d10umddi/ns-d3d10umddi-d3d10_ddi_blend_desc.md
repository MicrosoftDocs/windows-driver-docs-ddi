---
UID: NS:d3d10umddi.D3D10_DDI_BLEND_DESC
title: D3D10_DDI_BLEND_DESC
author: windows-driver-content
description: The D3D10_DDI_BLEND_DESC structure describes a blend state.
old-location: display\d3d10_ddi_blend_desc.htm
old-project: display
ms.assetid: dbb6e5ed-8d24-4b50-826b-f05f44de676a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D10_DDI_BLEND_DESC, D3D10_DDI_BLEND_DESC structure [Display Devices], UMDisplayDriver_Dx10param_Structs_8dd04d52-105b-4cc3-be87-5900625dcd6d.xml, d3d10umddi/D3D10_DDI_BLEND_DESC, display.d3d10_ddi_blend_desc
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D10_DDI_BLEND_DESC
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_BLEND_DESC
---

# D3D10_DDI_BLEND_DESC structure


## -description


The D3D10_DDI_BLEND_DESC structure describes a blend state.


## -syntax


````
typedef struct D3D10_DDI_BLEND_DESC {
  BOOL               AlphaToCoverageEnable;
  BOOL               BlendEnable[D3D10_DDI_SIMULTANEOUS_RENDER_TARGET_COUNT];
  D3D10_DDI_BLEND    SrcBlend;
  D3D10_DDI_BLEND    DestBlend;
  D3D10_DDI_BLEND_OP BlendOp;
  D3D10_DDI_BLEND    SrcBlendAlpha;
  D3D10_DDI_BLEND    DestBlendAlpha;
  D3D10_DDI_BLEND_OP BlendOpAlpha;
  UINT8              RenderTargetWriteMask[D3D10_DDI_SIMULTANEOUS_RENDER_TARGET_COUNT];
} D3D10_DDI_BLEND_DESC;
````


## -struct-fields




### -field AlphaToCoverageEnable

[in] A Boolean value that specifies whether transparency coverage is enabled. <b>TRUE</b> indicates transparency coverage is enabled; <b>FALSE</b> indicates transparency coverage is disabled. This member is relevant for multiple-sample antialiasing only.


### -field BlendEnable

[in] An array of Boolean values that specify whether blending is enabled for each associated render target. <b>TRUE</b> indicates blending is enabled; <b>FALSE</b> indicates blending is disabled. 


### -field SrcBlend


      [in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend.md">D3D10_DDI_BLEND</a>-typed value that indicates the blend mode of the source for all enabled render targets.
     


### -field DestBlend

[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend.md">D3D10_DDI_BLEND</a>-typed value that indicates the blend mode of the destination for all enabled render targets.


### -field BlendOp

[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend_op.md">D3D10_DDI_BLEND_OP</a>-typed value that indicates the blending operation for all enabled render targets.


### -field SrcBlendAlpha

[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend.md">D3D10_DDI_BLEND</a>-typed value that indicates the transparency blend mode of the source for all enabled render targets.


### -field DestBlendAlpha

[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend.md">D3D10_DDI_BLEND</a>-typed value that indicates the transparency blend mode of the destination for all enabled render targets.


### -field BlendOpAlpha

[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend_op.md">D3D10_DDI_BLEND_OP</a>-typed value that indicates the transparency blending operation for all enabled render targets.


### -field RenderTargetWriteMask

[in] An array of 8-bit bitwise values that indicate the write properties for each associated render target. Each bit of each element must be set to one of the following values from the D3D10_DDI_COLOR_WRITE_ENABLE enumeration.

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
 


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateblendstatesize.md">CalcPrivateBlendStateSize</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend_op.md">D3D10_DDI_BLEND_OP</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createblendstate.md">CreateBlendState</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_blend.md">D3D10_DDI_BLEND</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_BLEND_DESC structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

