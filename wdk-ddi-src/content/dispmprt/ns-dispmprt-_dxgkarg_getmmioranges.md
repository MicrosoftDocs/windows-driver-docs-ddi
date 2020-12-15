---
UID: NS:dispmprt._DXGKARG_GETMMIORANGES
title: _DXGKARG_GETMMIORANGES (dispmprt.h)
description: Arguments used to get the memory mapped input output (MMIO) range.
ms.date: 10/19/2018
keywords: ["DXGKARG_GETMMIORANGES structure"]
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
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - _DXGKARG_GETMMIORANGES
 - dispmprt/_DXGKARG_GETMMIORANGES
 - PDXGKARG_GETMMIORANGES
 - dispmprt/PDXGKARG_GETMMIORANGES
 - DXGKARG_GETMMIORANGES
 - dispmprt/DXGKARG_GETMMIORANGES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKARG_GETMMIORANGES
dev_langs:
 - c++
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

