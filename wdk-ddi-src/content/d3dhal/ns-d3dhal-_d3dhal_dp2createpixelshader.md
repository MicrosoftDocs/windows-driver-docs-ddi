---
UID: NS:d3dhal._D3DHAL_DP2CREATEPIXELSHADER
title: "_D3DHAL_DP2CREATEPIXELSHADER"
description: DirectX 8.0 and later versions only. The D3DHAL_DP2CREATEPIXELSHADER structure is used to create a pixel shader when a D3DDP2OP_CREATEPIXELSHADER opcode is received by D3dDrawPrimitives2.
old-location: display\d3dhal_dp2createpixelshader.htm
tech.root: display
ms.assetid: aa3a7f17-7210-458f-979b-1da455790e4a
ms.date: 05/10/2018
ms.keywords: "*LPD3DHAL_DP2CREATEPIXELSHADER, D3DHAL_DP2CREATEPIXELSHADER, D3DHAL_DP2CREATEPIXELSHADER structure [Display Devices], LPD3DHAL_DP2CREATEPIXELSHADER, LPD3DHAL_DP2CREATEPIXELSHADER structure pointer [Display Devices], _D3DHAL_DP2CREATEPIXELSHADER, d3dhal/D3DHAL_DP2CREATEPIXELSHADER, d3dhal/LPD3DHAL_DP2CREATEPIXELSHADER, d3dstrct_b17c15ca-697a-407b-b304-ac52ccf6ce6e.xml, display.d3dhal_dp2createpixelshader"
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
-	D3DHAL_DP2CREATEPIXELSHADER
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2CREATEPIXELSHADER
---

# _D3DHAL_DP2CREATEPIXELSHADER structure


## -description



   DirectX 8.0 and later versions only.
   

The D3DHAL_DP2CREATEPIXELSHADER structure is used to create a pixel shader when a D3DDP2OP_CREATEPIXELSHADER opcode is received by <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>.


## -struct-fields




### -field dwHandle

Specifies the handle to the pixel shader that is assigned by the runtime. This value is guaranteed to be subzero.


### -field dwCodeSize

Specifies the size, in bytes, of the shader code following this data structure in the DP2 stream.


## -remarks



The runtime generates a handle for this shader before calling the driver. The shader code itself follows the D3DHAL_DP2CREATEPIXELSHADER in the DP2 stream. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff552855">Direct3D Driver Shader Codes</a> for information about the format of an individual shader code and the tokens that comprise each shader code. 

Before calling the driver, the runtime validates the pixel shader code to ensure that it is legal for the specified shader language version.

It is important to note that the creation of a pixel shader does not imply the setting of the current shader.




## -see-also




D3DDP2OP_CREATEPIXELSHADER



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545689">D3DHAL_DP2PIXELSHADER</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>
 

 

