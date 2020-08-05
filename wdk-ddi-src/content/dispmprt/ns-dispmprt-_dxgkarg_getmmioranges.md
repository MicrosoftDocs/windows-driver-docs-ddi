---
UID: NS:dispmprt._DXGKARG_GETMMIORANGES
title: _DXGKARG_GETMMIORANGES (dispmprt.h)
description: Arguments used to get the memory mapped input output (MMIO) range.
ms.assetid: cb991a13-ccc5-4f20-a49f-e084ba38ca80
ms.date: 10/19/2018
keywords: ["DXGKARG_GETMMIORANGES structure"]
f1_keywords:
 - "dispmprt/_DXGKARG_GETMMIORANGES"
 - "_DXGKARG_GETMMIORANGES"
ms.keywords: _DXGKARG_GETMMIORANGES, DXGKARG_GETMMIORANGES, *PDXGKARG_GETMMIORANGES, 
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGKARG_GETMMIORANGES, *PDXGKARG_GETMMIORANGES
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- dispmprt.h
api_name: 
- _DXGKARG_GETMMIORANGES
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# _DXGKARG_GETMMIORANGES structure

## -description

Arguments used to get the memory mapped input output (MMIO) range.

## -struct-fields

### -field VirtualFunctionIndex

The particular Virtual function to query.

### -field BarIndex

The particular bar to query.

### -field NumRanges

The number of ranges in *pMmioRanges*.

### -field pMmioRanges
 
Pointer to an array of [DXGK_MMIORANGEINFO](ns-dispmprt-_dxgk_mmiorangeinfo.md) structures.

## -remarks

## -see-also

[DXGKDDI_GETMMIORANGES](nc-dispmprt-dxgkddi_getmmioranges.md) callback function
