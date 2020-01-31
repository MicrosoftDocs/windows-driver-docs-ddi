---
UID: NS:d3dumddi._D3DDDICB_RENDERFLAGS
title: _D3DDDICB_RENDERFLAGS (d3dumddi.h)
description: The D3DDDICB_RENDERFLAGS structure identifies information about a command buffer to be rendered.
old-location: display\d3dddicb_renderflags.htm
tech.root: display
ms.assetid: 18ae8ec2-a9e9-40e2-8b11-93fd163a801d
ms.date: 05/10/2018
ms.keywords: D3DDDICB_RENDERFLAGS, D3DDDICB_RENDERFLAGS structure [Display Devices], D3D_other_Structs_559cfa58-5c9b-470e-aa4b-6c145045ed82.xml, _D3DDDICB_RENDERFLAGS, d3dumddi/D3DDDICB_RENDERFLAGS, display.d3dddicb_renderflags
f1_keywords:
 - "d3dumddi/D3DDDICB_RENDERFLAGS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDICB_RENDERFLAGS
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_RENDERFLAGS
---

# _D3DDDICB_RENDERFLAGS structure


## -description


The D3DDDICB_RENDERFLAGS structure identifies information about a command buffer to be rendered.


## -struct-fields




### -field ResizeCommandBuffer

A UINT value that specifies whether to resize the command buffer. The driver puts the requested size in the <b>NewCommandBufferSize</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_render">D3DDDICB_RENDER</a> structure. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field ResizeAllocationList

A UINT value that specifies whether to resize the allocation list. The driver puts the requested number of elements in the <b>NewAllocationListSize</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_render">D3DDDICB_RENDER</a>. 

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field ResizePatchLocationList

A UINT value that specifies whether to resize the patch-location list. The driver puts the requested number of elements in the <b>NewPatchLocationListSize</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_render">D3DDDICB_RENDER</a>. 

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field NullRendering

A UINT value that specifies whether the graphics processing unit (GPU) should process any commands for the rendering context. The <b>NullRendering</b> bit-field flag is set to inform the GPU not to process any commands for the rendering context. The <b>NullRendering</b> bit-field flag is set only during performance investigating and debugging to simulate an infinitely fast rendering engine that still must perform the overhead of DMA buffer submission and signaling. <b>NullRendering</b> is never set during typical operations. 

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 28 bits (0xFFFFFFF0) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that is contained in D3DDDICB_RENDERFLAGS that can hold one 32-bit value that identifies information about a command buffer to be rendered.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_render">D3DDDICB_RENDER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb">pfnRenderCb</a>
 

 

