---
UID: NS:d3dumddi._D3DDDICB_RENDERFLAGS
title: "_D3DDDICB_RENDERFLAGS"
author: windows-driver-content
description: The D3DDDICB_RENDERFLAGS structure identifies information about a command buffer to be rendered.
old-location: display\d3dddicb_renderflags.htm
old-project: display
ms.assetid: 18ae8ec2-a9e9-40e2-8b11-93fd163a801d
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: d3dumddi/D3DDDICB_RENDERFLAGS, D3DDDICB_RENDERFLAGS structure [Display Devices], display.d3dddicb_renderflags, _D3DDDICB_RENDERFLAGS, D3D_other_Structs_559cfa58-5c9b-470e-aa4b-6c145045ed82.xml, D3DDDICB_RENDERFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDICB_RENDERFLAGS
product: Windows
targetos: Windows
req.typenames: D3DDDICB_RENDERFLAGS
---

# _D3DDDICB_RENDERFLAGS structure


## -description


The D3DDDICB_RENDERFLAGS structure identifies information about a command buffer to be rendered.


## -syntax


````
typedef struct _D3DDDICB_RENDERFLAGS {
  union {
    struct {
      UINT ResizeCommandBuffer  :1;
      UINT ResizeAllocationList  :1;
      UINT ResizePatchLocationList  :1;
      UINT NullRendering  :1;
      UINT Reserved  :28;
    };
    UINT   Value;
  };
} D3DDDICB_RENDERFLAGS;
````


## -struct-fields




### -field ResizeCommandBuffer

A UINT value that specifies whether to resize the command buffer. The driver puts the requested size in the <b>NewCommandBufferSize</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_render.md">D3DDDICB_RENDER</a> structure. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field ResizeAllocationList

A UINT value that specifies whether to resize the allocation list. The driver puts the requested number of elements in the <b>NewAllocationListSize</b> member of <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_render.md">D3DDDICB_RENDER</a>. 

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field ResizePatchLocationList

A UINT value that specifies whether to resize the patch-location list. The driver puts the requested number of elements in the <b>NewPatchLocationListSize</b> member of <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_render.md">D3DDDICB_RENDER</a>. 

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field NullRendering

A UINT value that specifies whether the graphics processing unit (GPU) should process any commands for the rendering context. The <b>NullRendering</b> bit-field flag is set to inform the GPU not to process any commands for the rendering context. The <b>NullRendering</b> bit-field flag is set only during performance investigating and debugging to simulate an infinitely fast rendering engine that still must perform the overhead of DMA buffer submission and signaling. <b>NullRendering</b> is never set during typical operations. 

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 28 bits (0xFFFFFFF0) of the 32-bit <b>Value</b> member to zeros.


#### - Value

A member in the union that is contained in D3DDDICB_RENDERFLAGS that can hold one 32-bit value that identifies information about a command buffer to be rendered.


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_render.md">D3DDDICB_RENDER</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_RENDERFLAGS structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

