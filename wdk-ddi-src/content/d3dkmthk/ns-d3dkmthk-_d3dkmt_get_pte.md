---
UID: NS:d3dkmthk._D3DKMT_GET_PTE
title: _D3DKMT_GET_PTE (d3dkmthk.h)
description: Used to get page table entries.
ms.assetid: bfe177b0-8922-438c-b214-e08f786b8e9c
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3dkmthk/_D3DKMT_GET_PTE"
ms.keywords: _D3DKMT_GET_PTE, D3DKMT_GET_PTE, 
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
req.typenames: D3DKMT_GET_PTE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- _D3DKMT_GET_PTE
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# _D3DKMT_GET_PTE structure

## -description

Used to get page table entries (PTE).

## -struct-fields

### -field PhysicalAdapterIndex

The physical adapter index in the LDA (linked display adapter) chain.

### -field PageTableLevel

The page table level.

### -field PageTableIndex

The page table index.

### -field b64KBPte

Indicates whether the page table is 64KB. This value is valid only when dual PTEs are supported.

### -field NumPtes

The number of PTEs to fill. 

### -field Pte

An array of PTEs.

### -field NumValidEntries
 
The number of valid entries.

## -remarks

## -see-also
