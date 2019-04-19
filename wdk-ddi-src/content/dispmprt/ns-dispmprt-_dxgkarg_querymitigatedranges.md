---
UID: NS:dispmprt._DXGKARG_QUERYMITIGATEDRANGES
title: _DXGKARG_QUERYMITIGATEDRANGES
author: windows-driver-content
description: Arguments used to query mitigated ranges.
tech.root: display
ms.assetid: c401fda9-9eaf-4d2b-a19e-d42b2c0cd9e8
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: struct
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
targetos: Windows
ms.custom: 19H1
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
