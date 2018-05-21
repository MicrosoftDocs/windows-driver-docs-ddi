---
UID: NS:d3dkmthk._D3DKMT_OPENSWAPCHAIN
title: _D3DKMT_OPENSWAPCHAIN
author: windows-driver-content
description:
ms.assetid: e4a4db5b-a3ab-45f2-bd3b-0bf808e2d6f8
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _D3DKMT_OPENSWAPCHAIN, D3DKMT_OPENSWAPCHAIN,
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
req.typenames: D3DKMT_OPENSWAPCHAIN
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	_D3DKMT_OPENSWAPCHAIN
product: Windows
targetos: Windows
---

# _D3DKMT_OPENSWAPCHAIN structure

## -description

Used to open a swap chain.

## -struct-fields

### -field hNtSwapChain

[in/out_opt] NT handle for swap chain in this process.

### -field pObjectAttributes

[in_opt] Security attributes of the swap chain.

### -field bProducer

[in] Indicates if producer or consumer.

### -field hDevice

[in] Handle to the device.

### -field bFailAcquireIfSurfaceBusy

[in] Indicates if acquires fail if surface still busy.

### -field DesiredAccess

[in] Desired access for the swap chain.

### -field DesiredAccessTextures

[in] Desired access for the textures.

### -field BufferAvailableEvent

[in_opt] Option handle to the event.

### -field SurfaceCount

[in/out] Number of buffers in the table provided on the way in, and out on number of surfaces used/needed.

### -field pNtSurfaceHandles

[out] Array of NT handles.

### -field bNonSequential

[out] Indicates if swap chain is sequential.

