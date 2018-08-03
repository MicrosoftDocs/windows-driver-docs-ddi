---
UID: NS:d3dkmthk._D3DKMT_ACQUIRESWAPCHAIN
title: _D3DKMT_ACQUIRESWAPCHAIN
author: windows-driver-content
description:
ms.assetid: 43e4b889-e55b-4921-8e41-e90698ac26f0
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _D3DKMT_ACQUIRESWAPCHAIN, D3DKMT_ACQUIRESWAPCHAIN,
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
req.typenames: D3DKMT_ACQUIRESWAPCHAIN
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	_D3DKMT_ACQUIRESWAPCHAIN
product: 
- Windows
targetos: Windows
---

# _D3DKMT_ACQUIRESWAPCHAIN structure

## -description

Used to get information about the swap chain.

## -struct-fields

### -field hNtSwapChain

[in] NT handle for the swap chain in this process.

### -field bReleaseBeforeAcquire

[in] Indicates if the caller wants to release the current buffer before acquire.

### -field bProducer

[in] Indicates if producer or consumer.

### -field ReleaseInfo

[in/out] Release info.

### -field AcquiredBufferIdx

[out] Index of the buffer that was just acquired.

### -field OpenerAcquiredSurfaceHandle

[out] Nt handle of texture that was just acquired, used only for non-sequential openers.

### -field AcquireMetadataSize

[out] Size of the metadata.
