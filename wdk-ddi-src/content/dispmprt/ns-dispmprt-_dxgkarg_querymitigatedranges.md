---
UID: NS:dispmprt._DXGKARG_QUERYMITIGATEDRANGES
title: _DXGKARG_QUERYMITIGATEDRANGES
description: Arguments used to query mitigated ranges.
tech.root: display
ms.date: 04/04/2019
keywords: ["DXGKARG_QUERYMITIGATEDRANGES structure"]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARG_QUERYMITIGATEDRANGES, DXGKARG_QUERYMITIGATEDRANGES, *PDXGKARG_QUERYMITIGATEDRANGES,
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
req.typenames: DXGKARG_QUERYMITIGATEDRANGES, *PDXGKARG_QUERYMITIGATEDRANGES
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _DXGKARG_QUERYMITIGATEDRANGES
 - dispmprt/_DXGKARG_QUERYMITIGATEDRANGES
 - PDXGKARG_QUERYMITIGATEDRANGES
 - dispmprt/PDXGKARG_QUERYMITIGATEDRANGES
 - DXGKARG_QUERYMITIGATEDRANGES
 - dispmprt/DXGKARG_QUERYMITIGATEDRANGES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKARG_QUERYMITIGATEDRANGES
product:
 - Windows
dev_langs:
 - c++
---

# _DXGKARG_QUERYMITIGATEDRANGES structure


## -description

Arguments used to query mitigated ranges.

## -struct-fields

### -field VirtualFunctionIndex

Zero-based offset of the Virtual Function from the first VF exposed by this Physical Function.

### -field BarIndex

The specific base address register to retrieve mitigations.

### -field NumRanges

Number of ranges to query.

### -field pMitigatedRange

 
A pointer to the array of mitigated ranges info.

## -remarks

## -see-also

