---
UID: NS:d3dumddi._D3DDDIARG_TEXBLT
title: "_D3DDDIARG_TEXBLT"
author: windows-driver-content
description: The D3DDDIARG_TEXBLT structure describes parameters for a texture bit-block transfer (bitblt) operation.
old-location: display\d3dddiarg_texblt.htm
tech.root: display
ms.assetid: e236ac2e-24d7-45a4-aa88-b496c8d92764
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_TEXBLT, D3DDDIARG_TEXBLT structure [Display Devices], UMDisplayDriver_param_Structs_4a343a1e-c364-4261-9f86-e179e0fc2f7c.xml, _D3DDDIARG_TEXBLT, d3dumddi/D3DDDIARG_TEXBLT, display.d3dddiarg_texblt
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	D3DDDIARG_TEXBLT
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_TEXBLT
---

# _D3DDDIARG_TEXBLT structure


## -description


The D3DDDIARG_TEXBLT structure describes parameters for a texture bit-block transfer (bitblt) operation. 


## -struct-fields




### -field hDstResource

[in] A handle to the destination resource.


### -field hSrcResource

[in] A handle to the source resource.


### -field CubeMapFace

[in] The face of a cube map.


### -field DstPoint

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569161">POINT</a> structure that describes the destination point where the source texture is copied.


### -field SrcRect

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that describes the source texture to copy to the destination point.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff569161">POINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>



<a href="https://msdn.microsoft.com/1ddfd822-7a43-4976-a153-ba862d6dfd82">TexBlt</a>
 

 

