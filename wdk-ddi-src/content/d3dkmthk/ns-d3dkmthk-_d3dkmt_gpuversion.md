---
UID: NS:d3dkmthk._D3DKMT_GPUVERSION
title: _D3DKMT_GPUVERSION (d3dkmthk.h)
description: Used to collect the bios version and GPU architecture name once during GPU initialization.
ms.assetid: 52bc5bb2-d9ea-4084-9ece-b7b65121ff73
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _D3DKMT_GPUVERSION, D3DKMT_GPUVERSION,
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
req.typenames: D3DKMT_GPUVERSION
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- _D3DKMT_GPUVERSION
product: 
- Windows
targetos: Windows
tech.root: display
---

# _D3DKMT_GPUVERSION structure

## -description

Used to collect the bios version and GPU architecture name once during GPU initialization.

## -struct-fields

### -field PhysicalAdapterIndex

The physical adapter index in the LDA (linked display adapter) chain.

### -field BiosVersion

The current bios of the adapter.

### -field GpuArchitecture

The gpu architecture of the adapter.
