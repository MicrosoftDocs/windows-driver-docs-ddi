---
UID: NS:dispmprt._DXGKARG_QUERYMITIGATEDRANGECOUNT
title: _DXGKARG_QUERYMITIGATEDRANGECOUNT
author: windows-driver-content
description: Arguments used to query mitigated range count.
tech.root: display
ms.assetid: f9cf3b82-a035-4089-9737-eeb1075a1ff7
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: struct
f1_keywords:
 - "dispmprt/_DXGKARG_QUERYMITIGATEDRANGECOUNT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARG_QUERYMITIGATEDRANGECOUNT, DXGKARG_QUERYMITIGATEDRANGECOUNT, *PDXGKARG_QUERYMITIGATEDRANGECOUNT, 
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
req.typenames: DXGKARG_QUERYMITIGATEDRANGECOUNT, *PDXGKARG_QUERYMITIGATEDRANGECOUNT
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - dispmprt.h
api_name: 
 - _DXGKARG_QUERYMITIGATEDRANGECOUNT
product: 
 - Windows
targetos: Windows
ms.custom: 19H1
---

# _DXGKARG_QUERYMITIGATEDRANGECOUNT structure

## -description

Arguments used to query mitigated range count.

## -struct-fields

### -field VirtualFunctionIndex

Zero-based offset of the Virtual Function from the first VF exposed by this Physical Function.

### -field RangeCount
 
The number of mitigated ranges for each base address register (BAR).

## -remarks

## -see-also
