---
UID: NS:d3d10umddi.D3D10_DDI_DEPTH_STENCILOP_DESC
title: D3D10_DDI_DEPTH_STENCILOP_DESC (d3d10umddi.h)
description: The D3D10_DDI_DEPTH_STENCILOP_DESC structure describes a depth stencil operation.
old-location: display\d3d10_ddi_depth_stencilop_desc.htm
ms.assetid: 3f0f3f1d-5b38-4815-9732-3b4079481c58
ms.date: 05/10/2018
ms.keywords: D3D10_DDI_DEPTH_STENCILOP_DESC, D3D10_DDI_DEPTH_STENCILOP_DESC structure [Display Devices], UMDisplayDriver_Dx10param_Structs_606e4f10-c713-4aae-b1d1-4a3c9ffde205.xml, d3d10umddi/D3D10_DDI_DEPTH_STENCILOP_DESC, display.d3d10_ddi_depth_stencilop_desc
ms.topic: struct
f1_keywords:
 - "d3d10umddi/D3D10_DDI_DEPTH_STENCILOP_DESC"
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
- D3D10_DDI_DEPTH_STENCILOP_DESC
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10_DDI_DEPTH_STENCILOP_DESC
---

# D3D10_DDI_DEPTH_STENCILOP_DESC structure


## -description


The D3D10_DDI_DEPTH_STENCILOP_DESC structure describes a depth stencil operation.


## -struct-fields




### -field StencilFailOp

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_ddi_stencil_op">D3D10_DDI_STENCIL_OP</a>-typed value that indicates the operation to perform if the stencil test fails.


### -field StencilDepthFailOp

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_ddi_stencil_op">D3D10_DDI_STENCIL_OP</a>-typed value that indicates the operation to perform if the stencil test passes and the depth test fails.


### -field StencilPassOp

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_ddi_stencil_op">D3D10_DDI_STENCIL_OP</a>-typed value that indicates the operation to perform if both stencil and depth tests pass.


### -field StencilFunc

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_ddi_comparison_func">D3D10_DDI_COMPARISON_FUNC</a>-typed value that indicates the stencil-comparison function to perform.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilstatesize">CalcPrivateDepthStencilStateSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdepthstencilstate">CreateDepthStencilState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_ddi_comparison_func">D3D10_DDI_COMPARISON_FUNC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_ddi_stencil_op">D3D10_DDI_STENCIL_OP</a>
 

 

