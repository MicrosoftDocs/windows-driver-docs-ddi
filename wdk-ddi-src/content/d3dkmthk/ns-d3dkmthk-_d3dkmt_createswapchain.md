---
UID: NS:d3dkmthk._D3DKMT_CREATESWAPCHAIN
title: _D3DKMT_CREATESWAPCHAIN (d3dkmthk.h)
description: Used to create a swap chain.
ms.assetid: 998e0e16-2680-4073-88a0-81d326d482a8
ms.date: 10/19/2018
keywords: ["_D3DKMT_CREATESWAPCHAIN structure"]
f1_keywords:
 - "d3dkmthk/_D3DKMT_CREATESWAPCHAIN"
 - "_D3DKMT_CREATESWAPCHAIN"
ms.keywords: _D3DKMT_CREATESWAPCHAIN, D3DKMT_CREATESWAPCHAIN,
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
req.typenames: D3DKMT_CREATESWAPCHAIN
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- _D3DKMT_CREATESWAPCHAIN
product: 
- Windows
targetos: Windows
tech.root: display
---

# _D3DKMT_CREATESWAPCHAIN structure

## -description

Used to create a swap chain.

## -struct-fields

### -field bProducer

[in] Indicates if producer or consumer.

### -field hDevice

[in] Handle to the device.

### -field pObjectAttributes

[in] Security attribute of swap chain.

### -field DesiredAccess

[in] Desired access for swap chain.

### -field SurfaceCount

[in] Number of buffers.

### -field pNtSurfaceHandles

[in] Array of NT handles.

### -field Flags

[in] Flags.

### -field BufferAvailableEvent

[in_opt] Option handle to event.

### -field hNtSwapChain

[out] NT handle for swap chain in this process.
