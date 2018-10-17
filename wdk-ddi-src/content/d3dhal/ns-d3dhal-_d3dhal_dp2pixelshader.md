---
UID: NS:d3dhal._D3DHAL_DP2PIXELSHADER
title: "_D3DHAL_DP2PIXELSHADER"
author: windows-driver-content
description: DirectX 8.0 and later versions only. The D3DHAL_DP2PIXELSHADER structure is used to set the current pixel shader, or delete a pixel shader, depending on the opcode received (D3DDP2OP_SETPIXELSHADER or D3DDP2OP_DELETEPIXELSHADER) by D3dDrawPrimitives2.
old-location: display\d3dhal_dp2pixelshader.htm
tech.root: display
ms.assetid: 820e7667-3adf-49c9-ab44-303f6ea7f4b2
ms.date: 5/10/2018
ms.keywords: "*LPD3DHAL_DP2PIXELSHADER, D3DHAL_DP2PIXELSHADER, D3DHAL_DP2PIXELSHADER structure [Display Devices], LPD3DHAL_DP2PIXELSHADER, LPD3DHAL_DP2PIXELSHADER structure pointer [Display Devices], _D3DHAL_DP2PIXELSHADER, d3dhal/D3DHAL_DP2PIXELSHADER, d3dhal/LPD3DHAL_DP2PIXELSHADER, d3dstrct_f9a920b0-9018-4b87-ab28-d0b50753195b.xml, display.d3dhal_dp2pixelshader"
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	d3dhal.h
api_name:
-	D3DHAL_DP2PIXELSHADER
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2PIXELSHADER
---

# _D3DHAL_DP2PIXELSHADER structure


## -description



   DirectX 8.0 and later versions only.
   

The D3DHAL_DP2PIXELSHADER structure is used to set the current pixel shader, or delete a pixel shader, depending on the opcode received (D3DDP2OP_SETPIXELSHADER or D3DDP2OP_DELETEPIXELSHADER) by <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>.


## -struct-fields




### -field dwHandle

Specifies the handle to the pixel shader that is assigned by the runtime. For delete requests, the handle is guaranteed to be subzero. For set requests, the handle can be zero. If set to zero, the driver should reset any programmable pixel state and revert to fixed function pixel processing behavior (for example, by using render states).


## -remarks



When switching from fixed function pixel processing to programmable vertex processing the values of, for example, legacy render states and texture stage states should be preserved. If and when a switch from programmable to fixed function pixel processing occurs (the driver receives a D3DDP2OP_SETPIXELSHADER with a shader handle of zero), that preserved state should be restored.

When switching between programmable shaders, any constant register that has a value specified in the definition of that shader should be set to that value. The values of all other constant registers should remain unchanged.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545467">D3DHAL_DP2CREATEPIXELSHADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545752">D3DHAL_DP2SETPIXELSHADERCONST</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>
 

 

