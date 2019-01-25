---
UID: NS:d3dkmthk._D3DKMT_REMOVESURFACEFROMSWAPCHAIN
title: "_D3DKMT_REMOVESURFACEFROMSWAPCHAIN" (d3dkmthk.h)
description: Used to remove a surface from the swap chain.
old-location: display\d3dkmt-removesurfacefromswapchain.htm
ms.assetid: 249a2bfc-7326-480f-bcc0-8d5104a9c890
ms.date: 05/10/2018
ms.keywords: D3DKMT_REMOVESURFACEFROMSWAPCHAIN, D3DKMT_REMOVESURFACEFROMSWAPCHAIN structure [Display Devices], _D3DKMT_REMOVESURFACEFROMSWAPCHAIN, d3dkmthk/D3DKMT_REMOVESURFACEFROMSWAPCHAIN, display.d3dkmt-removesurfacefromswapchain
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: 
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
-	d3dkmthk.h
api_name:
-	D3DKMT_REMOVESURFACEFROMSWAPCHAIN
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_REMOVESURFACEFROMSWAPCHAIN
---

# _D3DKMT_REMOVESURFACEFROMSWAPCHAIN structure


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Used to remove a surface from the swap chain.


## -struct-fields




### -field hNtSwapChain

The NT handle for the swapchain in this process.


### -field bProducer

Indicates if the handle is a producer or consumer.


### -field hNtSurfaceHandle

The NT handle of the surface to remove.


### -field BufferIdx

The buffer index of the surface to remove.

