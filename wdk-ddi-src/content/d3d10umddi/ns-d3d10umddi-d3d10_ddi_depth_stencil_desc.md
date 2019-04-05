---
UID: NS:d3d10umddi.D3D10_DDI_DEPTH_STENCIL_DESC
title: D3D10_DDI_DEPTH_STENCIL_DESC (d3d10umddi.h)
description: The D3D10_DDI_DEPTH_STENCIL_DESC structure describes a depth stencil state.
old-location: display\d3d10_ddi_depth_stencil_desc.htm
ms.assetid: d1043d5b-6f2c-4c2f-894a-ae6870865257
ms.date: 05/10/2018
ms.keywords: D3D10_DDI_DEPTH_STENCIL_DESC, D3D10_DDI_DEPTH_STENCIL_DESC structure [Display Devices], UMDisplayDriver_Dx10param_Structs_4e9cbeba-8eb3-43ea-891a-1b57c82cd3ef.xml, d3d10umddi/D3D10_DDI_DEPTH_STENCIL_DESC, display.d3d10_ddi_depth_stencil_desc
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3D10_DDI_DEPTH_STENCIL_DESC
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10_DDI_DEPTH_STENCIL_DESC
---

# D3D10_DDI_DEPTH_STENCIL_DESC structure


## -description


The D3D10_DDI_DEPTH_STENCIL_DESC structure describes a depth stencil state.


## -struct-fields




### -field DepthEnable

[in] A Boolean value that specifies whether depth is enabled. <b>TRUE</b> indicates depth is enabled; <b>FALSE</b> indicates depth is disabled. 


### -field DepthWriteMask

[in] A bitwise value that indicates the write properties for a depth stencil state. This member is a valid bitwise OR of the following values from the D3D10_DDI_DEPTH_WRITE_MASK enumeration.

|Value|Meaning|
|--- |--- |
|D3D10_DDI_DEPTH_WRITE_MASK_ZERO (0)|No properties|
|D3D10_DDI_DEPTH_WRITE_MASK_ALL (1)|All properties|
 


### -field DepthFunc

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541933">D3D10_DDI_COMPARISON_FUNC</a>-typed value that indicates the depth-comparison function to perform.


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

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541938">D3D10_DDI_DEPTH_STENCILOP_DESC</a> structure that describes the stencil operation to perform on forward-facing polygons.


### -field BackFace

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541938">D3D10_DDI_DEPTH_STENCILOP_DESC</a> structure that describes the stencil operation to perform on back-facing polygons.


## -remarks



If the <b>StencilEnable</b> member is set to <b>TRUE</b>, the <b>FrontEnable</b> member, <b>BackEnable</b> member, or both must also be set to <b>TRUE</b>. 




## -see-also




<a href="https://msdn.microsoft.com/dcc02e1e-97e0-4ccd-8329-8219cad5d09a">CalcPrivateDepthStencilStateSize</a>



<a href="https://msdn.microsoft.com/ed2da104-c4e8-43eb-80e0-10273b575020">CreateDepthStencilState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541933">D3D10_DDI_COMPARISON_FUNC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541938">D3D10_DDI_DEPTH_STENCILOP_DESC</a>
 

 

