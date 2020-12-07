---
UID: NS:d3dkmthk._D3DKMT_ADDSURFACETOSWAPCHAIN
title: _D3DKMT_ADDSURFACETOSWAPCHAIN (d3dkmthk.h)
description: Used to add a surface to the swapchain.
old-location: display\d3dkmt-addsurfacetoswapchain.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_ADDSURFACETOSWAPCHAIN structure"]
ms.keywords: D3DKMT_ADDSURFACETOSWAPCHAIN, D3DKMT_ADDSURFACETOSWAPCHAIN structure [Display Devices], _D3DKMT_ADDSURFACETOSWAPCHAIN, d3dkmthk/D3DKMT_ADDSURFACETOSWAPCHAIN, display.d3dkmt-addsurfacetoswapchain
f1_keywords:
 - "d3dkmthk/D3DKMT_ADDSURFACETOSWAPCHAIN"
 - "D3DKMT_ADDSURFACETOSWAPCHAIN"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- D3DKMT_ADDSURFACETOSWAPCHAIN
targetos: Windows
tech.root: display
req.typenames: D3DKMT_ADDSURFACETOSWAPCHAIN
---

# _D3DKMT_ADDSURFACETOSWAPCHAIN structure


## -description


Used to add a surface to the swapchain.


## -struct-fields




### -field hNtSwapChain

An NT handle for the swapchain in this process.


### -field bProducer

Indicates if the surface is a producer or consumer.


### -field hNtSurfaceHandle

An NT handle for the surface to be added.


### -field BufferIdx

Index of were the texture was placed on the surface table.

