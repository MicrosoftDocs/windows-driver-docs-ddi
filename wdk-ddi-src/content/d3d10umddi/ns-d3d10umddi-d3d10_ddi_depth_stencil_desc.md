---
UID: NS:d3d10umddi.D3D10_DDI_DEPTH_STENCIL_DESC
title: D3D10_DDI_DEPTH_STENCIL_DESC
author: windows-driver-content
description: The D3D10_DDI_DEPTH_STENCIL_DESC structure describes a depth stencil state.
old-location: display\d3d10_ddi_depth_stencil_desc.htm
old-project: display
ms.assetid: d1043d5b-6f2c-4c2f-894a-ae6870865257
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3d10_ddi_depth_stencil_desc, D3D10_DDI_DEPTH_STENCIL_DESC structure [Display Devices], D3D10_DDI_DEPTH_STENCIL_DESC, UMDisplayDriver_Dx10param_Structs_4e9cbeba-8eb3-43ea-891a-1b57c82cd3ef.xml, d3d10umddi/D3D10_DDI_DEPTH_STENCIL_DESC
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
-	D3D10_DDI_DEPTH_STENCIL_DESC
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_DEPTH_STENCIL_DESC
---

# D3D10_DDI_DEPTH_STENCIL_DESC structure


## -description


The D3D10_DDI_DEPTH_STENCIL_DESC structure describes a depth stencil state.


## -syntax


````
typedef struct D3D10_DDI_DEPTH_STENCIL_DESC {
  BOOL                           DepthEnable;
  D3D10_DDI_DEPTH_WRITE_MASK     DepthWriteMask;
  D3D10_DDI_COMPARISON_FUNC      DepthFunc;
  BOOL                           StencilEnable;
  BOOL                           FrontEnable;
  BOOL                           BackEnable;
  UINT8                          StencilReadMask;
  UINT8                          StencilWriteMask;
  D3D10_DDI_DEPTH_STENCILOP_DESC FrontFace;
  D3D10_DDI_DEPTH_STENCILOP_DESC BackFace;
} D3D10_DDI_DEPTH_STENCIL_DESC;
````


## -struct-fields




### -field DepthEnable

[in] A Boolean value that specifies whether depth is enabled. <b>TRUE</b> indicates depth is enabled; <b>FALSE</b> indicates depth is disabled. 


### -field DepthWriteMask

[in] A bitwise value that indicates the write properties for a depth stencil state. This member is a valid bitwise OR of the following values from the D3D10_DDI_DEPTH_WRITE_MASK enumeration.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3D10_DDI_DEPTH_WRITE_MASK_ZERO (0)

</td>
<td>
No properties

</td>
</tr>
<tr>
<td>
D3D10_DDI_DEPTH_WRITE_MASK_ALL (1)

</td>
<td>
All properties

</td>
</tr>
</table> 


### -field DepthFunc

[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_comparison_func.md">D3D10_DDI_COMPARISON_FUNC</a>-typed value that indicates the depth-comparison function to perform.


### -field StencilEnable

[in] A Boolean value that specifies whether stencil is enabled. <b>TRUE</b> indicates stencil is enabled; <b>FALSE</b> indicates stencil is disabled. 


### -field FrontEnable

[in] A Boolean value that specifies whether the performance of stencil operations on forward-facing polygons is enabled. <b>TRUE</b> indicates that the performance on forward-facing polygons is enabled; <b>FALSE</b> indicates that it is disabled. 


### -field BackEnable

[in] A Boolean value that specifies whether the performance of stencil operations on back-facing polygons is enabled. <b>TRUE</b> indicates that the performance on back-facing polygons is enabled; <b>FALSE</b> indicates that it is disabled. 


### -field StencilReadMask

[in] An 8-bit bitwise value that the driver uses in a bitwise AND operation with the stencil value in the stencil buffer immediately after reading the stencil value out of the stencil buffer. 


### -field StencilWriteMask

[in] An 8-bit bitwise value that the driver uses in a bitwise AND operation with the current stencil value before writing the result back out to the stencil buffer. 


### -field FrontFace

[in] A <a href="..\d3d10umddi\ns-d3d10umddi-d3d10_ddi_depth_stencilop_desc.md">D3D10_DDI_DEPTH_STENCILOP_DESC</a> structure that describes the stencil operation to perform on forward-facing polygons.


### -field BackFace

[in] A <a href="..\d3d10umddi\ns-d3d10umddi-d3d10_ddi_depth_stencilop_desc.md">D3D10_DDI_DEPTH_STENCILOP_DESC</a> structure that describes the stencil operation to perform on back-facing polygons.


## -remarks


If the <b>StencilEnable</b> member is set to <b>TRUE</b>, the <b>FrontEnable</b> member, <b>BackEnable</b> member, or both must also be set to <b>TRUE</b>. 



## -see-also

<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_comparison_func.md">D3D10_DDI_COMPARISON_FUNC</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdepthstencilstate.md">CreateDepthStencilState</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_ddi_depth_stencilop_desc.md">D3D10_DDI_DEPTH_STENCILOP_DESC</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilstatesize.md">CalcPrivateDepthStencilStateSize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_DEPTH_STENCIL_DESC structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

