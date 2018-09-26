---
UID: NS:dispmprt._DXGKARG_GETMMIORANGES
title: _DXGKARG_GETMMIORANGES
author: windows-driver-content
description: Arguments used to get the memory mapped input output (MMIO) range.
ms.assetid: cb991a13-ccc5-4f20-a49f-e084ba38ca80
ms.author: windowsdriverdev
ms.date: 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARG_GETMMIORANGES, DXGKARG_GETMMIORANGES, *PDXGKARG_GETMMIORANGES, 
req.header: dispmprt.h
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
req.typenames: DXGKARG_GETMMIORANGES, *PDXGKARG_GETMMIORANGES
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	dispmprt.h
api_name: 
-	_DXGKARG_GETMMIORANGES
product:
-	Windows
targetos: Windows
tech.root: display
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