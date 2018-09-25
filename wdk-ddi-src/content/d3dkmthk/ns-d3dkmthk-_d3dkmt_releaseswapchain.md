---
UID: NS:d3dkmthk._D3DKMT_RELEASESWAPCHAIN
title: _D3DKMT_RELEASESWAPCHAIN
author: windows-driver-content
description: Release the swap chain.
ms.assetid: bce1cc2a-5e38-4a35-b2a2-44adbf5e0117
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _D3DKMT_RELEASESWAPCHAIN, D3DKMT_RELEASESWAPCHAIN,
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DKMT_RELEASESWAPCHAIN
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	_D3DKMT_RELEASESWAPCHAIN
product: 
- Windows
targetos: Windows
tech.root: display
---

# _D3DKMT_RELEASESWAPCHAIN structure

## -description

Release the swap chain.

## -struct-fields

### -field hNtSwapChain

[in] NT handle for swap chain in this process.

### -field bProducer

[in] Indicates if producer or consumer.

### -field MetaDataSize

[in] Size of metadata.

### -field pMetaData

[in] Point to metadata for frame.

### -field DeferredFreeListSize

[in/out] On entry the size of the pDeferredFreeList table, on exit the number of entries used.

### -field pDeferredFreeList

[out] List of surfaces that have been removed.

