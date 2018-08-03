---
UID: NS:d3d10umddi.D3D10DDIARG_TEX2D_DEPTHSTENCILVIEW
title: D3D10DDIARG_TEX2D_DEPTHSTENCILVIEW
author: windows-driver-content
description: The D3D10DDIARG_TEX2D_DEPTHSTENCILVIEW structure describes a two-dimensional (2-D) texture that is used to create a depth stencil view in a call to the CreateDepthStencilView function.
old-location: display\d3d10ddiarg_tex2d_depthstencilview.htm
tech.root: display
ms.assetid: f659584f-e0a5-46b6-b20d-c19aba421114
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3D10DDIARG_TEX2D_DEPTHSTENCILVIEW, D3D10DDIARG_TEX2D_DEPTHSTENCILVIEW structure [Display Devices], UMDisplayDriver_Dx10param_Structs_6887e338-dbab-4f35-bce1-e4412598d9bc.xml, d3d10umddi/D3D10DDIARG_TEX2D_DEPTHSTENCILVIEW, display.d3d10ddiarg_tex2d_depthstencilview
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
-	D3D10DDIARG_TEX2D_DEPTHSTENCILVIEW
product:
- Windows
targetos: Windows
req.typenames: D3D10DDIARG_TEX2D_DEPTHSTENCILVIEW
---

# D3D10DDIARG_TEX2D_DEPTHSTENCILVIEW structure


## -description


The D3D10DDIARG_TEX2D_DEPTHSTENCILVIEW structure describes a two-dimensional (2-D) texture that is used to create a depth stencil view in a call to the <a href="https://msdn.microsoft.com/1a1c28f0-8343-4255-8055-d31eb643b7d5">CreateDepthStencilView</a> function. 


## -struct-fields




### -field MipSlice

[in] The identifier of the MIP-map slice. 


### -field FirstArraySlice

[in] The identifier of the first array slice. 


### -field ArraySize

[in] The number of array slices for the texture. 


## -see-also




<a href="https://msdn.microsoft.com/e5dfa018-f9a5-467f-8e84-9697d5f94689">CalcPrivateDepthStencilViewSize</a>



<a href="https://msdn.microsoft.com/1a1c28f0-8343-4255-8055-d31eb643b7d5">CreateDepthStencilView</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541658">D3D10DDIARG_CREATEDEPTHSTENCILVIEW</a>
 

 

