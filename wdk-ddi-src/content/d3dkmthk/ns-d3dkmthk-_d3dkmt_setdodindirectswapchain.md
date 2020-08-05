---
UID: NS:d3dkmthk._D3DKMT_SETDODINDIRECTSWAPCHAIN
title: _D3DKMT_SETDODINDIRECTSWAPCHAIN (d3dkmthk.h)
description: Used to set the device owner display's (DOD) indirect swap chain resources.
ms.assetid: 1361b90e-5462-44ba-b117-c83fe4c6c040
ms.date: 10/19/2018
keywords: ["D3DKMT_SETDODINDIRECTSWAPCHAIN structure"]
f1_keywords:
 - "d3dkmthk/_D3DKMT_SETDODINDIRECTSWAPCHAIN"
 - "_D3DKMT_SETDODINDIRECTSWAPCHAIN"
ms.keywords: _D3DKMT_SETDODINDIRECTSWAPCHAIN, D3DKMT_SETDODINDIRECTSWAPCHAIN, 
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
req.typenames: D3DKMT_SETDODINDIRECTSWAPCHAIN
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- _D3DKMT_SETDODINDIRECTSWAPCHAIN
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# _D3DKMT_SETDODINDIRECTSWAPCHAIN structure

## -description

Used to set the device owner display's (DOD) indirect swap chain resources.

## -struct-fields

### -field hDodAdapter

[in] A handle to the DOD (device owner's display) adapter.

### -field hDevice

[in] A handle to the device.

### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the monitor is connected to.

### -field hNtSwapChain

[in] NT handle for swap chain in this process.

### -field bTerminateOutput
 
[in] Swap chain owner is reporting a device timeout.

## -remarks

## -see-also
