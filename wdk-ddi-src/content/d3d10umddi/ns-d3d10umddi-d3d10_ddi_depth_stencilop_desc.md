---
UID: NS:d3d10umddi.D3D10_DDI_DEPTH_STENCILOP_DESC
title: D3D10_DDI_DEPTH_STENCILOP_DESC
author: windows-driver-content
description: The D3D10_DDI_DEPTH_STENCILOP_DESC structure describes a depth stencil operation.
old-location: display\d3d10_ddi_depth_stencilop_desc.htm
old-project: display
ms.assetid: 3f0f3f1d-5b38-4815-9732-3b4079481c58
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3D10_DDI_DEPTH_STENCILOP_DESC, D3D10_DDI_DEPTH_STENCILOP_DESC structure [Display Devices], UMDisplayDriver_Dx10param_Structs_606e4f10-c713-4aae-b1d1-4a3c9ffde205.xml, d3d10umddi/D3D10_DDI_DEPTH_STENCILOP_DESC, display.d3d10_ddi_depth_stencilop_desc
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
-	D3D10_DDI_DEPTH_STENCILOP_DESC
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_DEPTH_STENCILOP_DESC
---

# D3D10_DDI_DEPTH_STENCILOP_DESC structure


## -description


The D3D10_DDI_DEPTH_STENCILOP_DESC structure describes a depth stencil operation.


## -syntax


````
typedef struct D3D10_DDI_DEPTH_STENCILOP_DESC {
  D3D10_DDI_STENCIL_OP      StencilFailOp;
  D3D10_DDI_STENCIL_OP      StencilDepthFailOp;
  D3D10_DDI_STENCIL_OP      StencilPassOp;
  D3D10_DDI_COMPARISON_FUNC StencilFunc;
} D3D10_DDI_DEPTH_STENCILOP_DESC;
````


## -struct-fields




### -field StencilFailOp

[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_stencil_op.md">D3D10_DDI_STENCIL_OP</a>-typed value that indicates the operation to perform if the stencil test fails.


### -field StencilDepthFailOp

[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_stencil_op.md">D3D10_DDI_STENCIL_OP</a>-typed value that indicates the operation to perform if the stencil test passes and the depth test fails.


### -field StencilPassOp

[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_stencil_op.md">D3D10_DDI_STENCIL_OP</a>-typed value that indicates the operation to perform if both stencil and depth tests pass.


### -field StencilFunc

[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_comparison_func.md">D3D10_DDI_COMPARISON_FUNC</a>-typed value that indicates the stencil-comparison function to perform.


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdepthstencilstate.md">CreateDepthStencilState</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilstatesize.md">CalcPrivateDepthStencilStateSize</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_stencil_op.md">D3D10_DDI_STENCIL_OP</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_comparison_func.md">D3D10_DDI_COMPARISON_FUNC</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_DEPTH_STENCILOP_DESC structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

