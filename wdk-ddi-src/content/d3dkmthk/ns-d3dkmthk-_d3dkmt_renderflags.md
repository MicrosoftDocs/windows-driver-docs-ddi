---
UID: NS:d3dkmthk._D3DKMT_RENDERFLAGS
title: "_D3DKMT_RENDERFLAGS"
author: windows-driver-content
description: The D3DKMT_RENDERFLAGS structure identifies the type of command buffer to be rendered in a call to the D3DKMTRender function.
old-location: display\d3dkmt_renderflags.htm
old-project: display
ms.assetid: 6a25528c-063b-4cd5-963d-82245009bb48
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 3, A, D, D3DKMT_RENDERFLAGS, D3DKMT_RENDERFLAGS structure [Display Devices], E, F, G, K, L, M, N, OpenGL_Structs_8a885a03-0eba-4119-973a-a1c1dafe3c10.xml, R, S, T, _, _D3DKMT_RENDERFLAGS, d3dkmthk/D3DKMT_RENDERFLAGS, display.d3dkmt_renderflags"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_RENDERFLAGS
product: Windows
targetos: Windows
req.typenames: D3DKMT_RENDERFLAGS
---

# _D3DKMT_RENDERFLAGS structure


## -description


The D3DKMT_RENDERFLAGS structure identifies the type of command buffer to be rendered in a call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtrender.md">D3DKMTRender</a> function.


## -syntax


````
typedef struct _D3DKMT_RENDERFLAGS {
  UINT ResizeCommandBuffer  :1;
  UINT ResizeAllocationList  :1;
  UINT ResizePatchLocationList  :1;
  UINT NullRendering  :1;
  UINT PresentRedirected  :1;
  UINT RenderKm  :1;
  UINT Reserved  :26;
} D3DKMT_RENDERFLAGS;
````


## -struct-fields




### -field ResizeCommandBuffer

A UINT value that specifies whether to resize the command buffer. The driver puts the requested size in the <b>NewCommandBufferSize</b> member of the <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_render.md">D3DKMT_RENDER</a> structure. Because a resize request by the driver might not be possible, the driver must always verify the size value that is returned.

Setting this member is equivalent to setting the first bit of a 32-bit value (0x00000001).


### -field ResizeAllocationList

A UINT value that specifies whether to resize the allocation list. The driver puts the requested number of elements in the <b>NewAllocationListSize</b> member of the <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_render.md">D3DKMT_RENDER</a> structure. Because a resize request by the driver might not be possible, the driver must always verify the size value that is returned.

Setting this member is equivalent to setting the second bit of a 32-bit value (0x00000002).


### -field ResizePatchLocationList

A UINT value that specifies whether to resize the patch-location list. The driver puts the requested number of elements in the <b>NewPatchLocationListSize</b> member of the <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_render.md">D3DKMT_RENDER</a> structure. Because a resize request by the driver might not be possible, the driver must always verify the size value that is returned.

Setting this member is equivalent to setting the third bit of a 32-bit value (0x00000004).


### -field NullRendering

A UINT value that specifies whether the graphics processing unit (GPU) should process any commands for the rendering context. The <b>NullRendering</b> bit-field flag is set to inform the GPU not to process any commands for the rendering context. The <b>NullRendering</b> bit-field flag is set only during performance investigating and debugging to simulate an infinitely fast rendering engine that still must perform the overhead of DMA buffer submission and signaling. <b>NullRendering</b> is never set during typical operations. 

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field PresentRedirected

A UINT value that specifies whether to redirect the present command. The command contains a completion of one frame even though the command was completed in the OpenGl ICD.

Setting this member is equivalent to setting the fifth bit of a 32-bit value (0x00000010).


### -field RenderKm

Supported in Windows 7 and later versions.

A UINT value that specifies whether the OpenGL ICD supplies a pointer to the command buffer to be rendered in the ICD's call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtrender.md">D3DKMTRender</a> function. If this flag is set, the runtime does not call the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_render.md">DxgkDdiRender</a> function. If this flag is set, the runtime calls the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_renderkm.md">DxgkDdiRenderKm</a> function. 

Setting this member is equivalent to setting the sixth bit of a 32-bit value (0x00000020).


### -field RenderKmReadback

 


### -field Reserved

This member is reserved and should be set to zero. Setting this member is equivalent to setting the remaining 26 bits (0xFFFFFFC0) of a 32-bit value to zeros.


## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_render.md">D3DKMT_RENDER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_RENDERFLAGS structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

