---
UID: NS:d3dkmthk._D3DKMT_GETSETSWAPCHAINMETADATA
title: _D3DKMT_GETSETSWAPCHAINMETADATA (d3dkmthk.h)
description: Used to get swap chain metadata.
ms.assetid: 172bdd24-db38-43e1-b703-0c8d01b06520
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3dkmthk/_D3DKMT_GETSETSWAPCHAINMETADATA"
ms.keywords: _D3DKMT_GETSETSWAPCHAINMETADATA, D3DKMT_GETSETSWAPCHAINMETADATA, 
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
req.typenames: D3DKMT_GETSETSWAPCHAINMETADATA
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- _D3DKMT_GETSETSWAPCHAINMETADATA
product:
- Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# _D3DKMT_GETSETSWAPCHAINMETADATA structure

## -description

Used to get swap chain metadata.

## -struct-fields

### -field hNtSwapChain

[in] NT handle for swap chain in this process.

### -field bSetMetaData

[in] Indicates if caller is setting or getting the metadata.

### -field bProducer

[in] Indicates if producer or consumer.

### -field bGlobalMetaData

[in] Indicates if the caller is setting the swap-chain global metadata, or surface metadata.

### -field BufferSize

[in] Size of buffer for metadata to be copied to.

### -field pBuffer

[in, out] Buffer metadata should be copied to.

### -field DataCopied
 
[out] Number of bytes copied to the buffer.

## -remarks

## -see-also
