---
UID: NS:d3dkmthk._D3DKMT_UNORDEREDPRESENTSWAPCHAIN
title: _D3DKMT_UNORDEREDPRESENTSWAPCHAIN (d3dkmthk.h)
description: Used to store information about the swapchain being presented.
old-location: display\d3dkmt-unorderedpresentswapchain.htm
ms.assetid: c8b13348-71a6-4981-8c99-6368fa0f01ff
ms.date: 05/10/2018
keywords: ["D3DKMT_UNORDEREDPRESENTSWAPCHAIN structure"]
ms.keywords: D3DKMT_UNORDEREDPRESENTSWAPCHAIN, D3DKMT_UNORDEREDPRESENTSWAPCHAIN structure [Display Devices], _D3DKMT_UNORDEREDPRESENTSWAPCHAIN, d3dkmthk/D3DKMT_UNORDEREDPRESENTSWAPCHAIN, display.d3dkmt-unorderedpresentswapchain
f1_keywords:
 - "d3dkmthk/D3DKMT_UNORDEREDPRESENTSWAPCHAIN"
 - "D3DKMT_UNORDEREDPRESENTSWAPCHAIN"
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
- D3DKMT_UNORDEREDPRESENTSWAPCHAIN
targetos: Windows
tech.root: display
req.typenames: D3DKMT_UNORDEREDPRESENTSWAPCHAIN
---

# _D3DKMT_UNORDEREDPRESENTSWAPCHAIN structure


## -description


Used to store information about the swap chain being presented.


## -struct-fields




### -field hNtSwapChain

[in] NT handle for the swapchain in this process.


### -field bProducer

[in] Indicates if producer or consumer.


### -field PresentBufferIdx

[in] Index of the buffer to present.


### -field MetaDataSize

[in] Size of the metadata.


### -field pMetaData

[in] A pointer to the metadata for the frame.

### -field hNtPresentSurfaceHandle

[in] NT Handle of surface to present
