---
UID: NS:d3dkmthk._D3DKMT_REMOVESURFACEFROMSWAPCHAIN
title: "_D3DKMT_REMOVESURFACEFROMSWAPCHAIN"
author: windows-driver-content
description: Used to remove a surface from the swap chain.
old-location: display\d3dkmt-removesurfacefromswapchain.htm
old-project: display
ms.assetid: 249a2bfc-7326-480f-bcc0-8d5104a9c890
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_D3DKMT_REMOVESURFACEFROMSWAPCHAIN, d3dkmthk/D3DKMT_REMOVESURFACEFROMSWAPCHAIN, D3DKMT_REMOVESURFACEFROMSWAPCHAIN, display.d3dkmt-removesurfacefromswapchain, D3DKMT_REMOVESURFACEFROMSWAPCHAIN structure [Display Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_REMOVESURFACEFROMSWAPCHAIN
product: Windows
targetos: Windows
req.typenames: D3DKMT_REMOVESURFACEFROMSWAPCHAIN
---

# _D3DKMT_REMOVESURFACEFROMSWAPCHAIN structure


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Used to remove a surface from the swap chain.


## -syntax


````
typedef struct _D3DKMT_REMOVESURFACEFROMSWAPCHAIN {
  HANDLE hNtSwapChain;
  BOOL   bProducer;
  HANDLE hNtSurfaceHandle;
  UINT   BufferIdx;
} D3DKMT_REMOVESURFACEFROMSWAPCHAIN;
````


## -struct-fields




### -field hNtSwapChain

The NT handle for the swapchain in this process.


### -field bProducer

Indicates if the handle is a producer or consumer.


### -field hNtSurfaceHandle

The NT handle of the surface to remove.


### -field BufferIdx

The buffer index of the surface to remove.

