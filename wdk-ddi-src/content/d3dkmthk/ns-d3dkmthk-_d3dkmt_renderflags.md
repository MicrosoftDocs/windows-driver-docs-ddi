---
UID: NS:d3dkmthk._D3DKMT_RENDERFLAGS
title: "_D3DKMT_RENDERFLAGS"
author: windows-driver-content
description: The D3DKMT_RENDERFLAGS structure identifies the type of command buffer to be rendered in a call to the D3DKMTRender function.
old-location: display\d3dkmt_renderflags.htm
old-project: display
ms.assetid: 6a25528c-063b-4cd5-963d-82245009bb48
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_RENDERFLAGS, D3DKMT_RENDERFLAGS structure [Display Devices], OpenGL_Structs_8a885a03-0eba-4119-973a-a1c1dafe3c10.xml, _D3DKMT_RENDERFLAGS, d3dkmthk/D3DKMT_RENDERFLAGS, display.d3dkmt_renderflags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	d3dkmthk.h
api_name:
-	D3DKMT_RENDERFLAGS
product: Windows
targetos: Windows
req.typenames: D3DKMT_RENDERFLAGS
---

# _D3DKMT_RENDERFLAGS structure


## -description


The D3DKMT_RENDERFLAGS structure identifies the type of command buffer to be rendered in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547145">D3DKMTRender</a> function.


## -struct-fields




### -field ResizeCommandBuffer

A UINT value that specifies whether to resize the command buffer. The driver puts the requested size in the <b>NewCommandBufferSize</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548238">D3DKMT_RENDER</a> structure. Because a resize request by the driver might not be possible, the driver must always verify the size value that is returned.

Setting this member is equivalent to setting the first bit of a 32-bit value (0x00000001).


### -field ResizeAllocationList

A UINT value that specifies whether to resize the allocation list. The driver puts the requested number of elements in the <b>NewAllocationListSize</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548238">D3DKMT_RENDER</a> structure. Because a resize request by the driver might not be possible, the driver must always verify the size value that is returned.

Setting this member is equivalent to setting the second bit of a 32-bit value (0x00000002).


### -field ResizePatchLocationList

A UINT value that specifies whether to resize the patch-location list. The driver puts the requested number of elements in the <b>NewPatchLocationListSize</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548238">D3DKMT_RENDER</a> structure. Because a resize request by the driver might not be possible, the driver must always verify the size value that is returned.

Setting this member is equivalent to setting the third bit of a 32-bit value (0x00000004).


### -field NullRendering

A UINT value that specifies whether the graphics processing unit (GPU) should process any commands for the rendering context. The <b>NullRendering</b> bit-field flag is set to inform the GPU not to process any commands for the rendering context. The <b>NullRendering</b> bit-field flag is set only during performance investigating and debugging to simulate an infinitely fast rendering engine that still must perform the overhead of DMA buffer submission and signaling. <b>NullRendering</b> is never set during typical operations. 

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field PresentRedirected

A UINT value that specifies whether to redirect the present command. The command contains a completion of one frame even though the command was completed in the OpenGl ICD.

Setting this member is equivalent to setting the fifth bit of a 32-bit value (0x00000010).


### -field RenderKm

Supported in Windows 7 and later versions.

A UINT value that specifies whether the OpenGL ICD supplies a pointer to the command buffer to be rendered in the ICD's call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547145">D3DKMTRender</a> function. If this flag is set, the runtime does not call the display miniport driver's <a href="https://msdn.microsoft.com/fd634768-5e1e-4f40-82fd-5ef69148c3d7">DxgkDdiRender</a> function. If this flag is set, the runtime calls the display miniport driver's <a href="https://msdn.microsoft.com/5841934d-7e0a-4bb8-a7f8-17d8c0af351f">DxgkDdiRenderKm</a> function. 

Setting this member is equivalent to setting the sixth bit of a 32-bit value (0x00000020).


### -field RenderKmReadback

 


### -field Reserved

This member is reserved and should be set to zero. Setting this member is equivalent to setting the remaining 26 bits (0xFFFFFFC0) of a 32-bit value to zeros.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548238">D3DKMT_RENDER</a>
 

 

