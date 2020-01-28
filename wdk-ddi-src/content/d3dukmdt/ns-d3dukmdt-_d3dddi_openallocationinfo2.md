---
UID: NS:d3dukmdt._D3DDDI_OPENALLOCATIONINFO2
title: _D3DDDI_OPENALLOCATIONINFO2 (d3dukmdt.h)
description: The D3DDDI_OPENALLOCATIONINFO2 structure describes an allocation to be opened.
ms.assetid: aade2040-999b-4094-b984-cf0ed7324c6a
ms.date: 10/19/2018
f1_keywords:
 - "d3dukmdt/_D3DDDI_OPENALLOCATIONINFO2"
ms.keywords: _D3DDDI_OPENALLOCATIONINFO2, D3DDDI_OPENALLOCATIONINFO2, 
req.header: d3dukmdt.h
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
req.typenames: D3DDDI_OPENALLOCATIONINFO2
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dukmdt.h
api_name: 
- _D3DDDI_OPENALLOCATIONINFO2
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# _D3DDDI_OPENALLOCATIONINFO2 structure

## -description

The D3DDDI_OPENALLOCATIONINFO2 structure describes an allocation to be opened.

## -struct-fields

### -field hAllocation

[in] Handle for this allocation in this process.

### -field pPrivateDriverData

[in] Pointer to driver private buffer for this allocation.

### -field PrivateDriverDataSize

[in] Size in bytes of driver private buffer for this allocation.

### -field GpuVirtualAddress

[out] The GPU virtual address of the allocation opened.

### -field Reserved

Reserved.

## -remarks

## -see-also
