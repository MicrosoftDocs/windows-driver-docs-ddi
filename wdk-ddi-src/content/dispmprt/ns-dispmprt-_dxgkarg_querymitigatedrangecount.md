---
UID: NS:dispmprt._DXGKARG_QUERYMITIGATEDRANGECOUNT
title: _DXGKARG_QUERYMITIGATEDRANGECOUNT
description: Arguments used to query mitigated range count.
tech.root: display
ms.date: 04/04/2019
keywords: ["DXGKARG_QUERYMITIGATEDRANGECOUNT structure"]
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
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _DXGKARG_QUERYMITIGATEDRANGECOUNT
 - dispmprt/_DXGKARG_QUERYMITIGATEDRANGECOUNT
 - PDXGKARG_QUERYMITIGATEDRANGECOUNT
 - dispmprt/PDXGKARG_QUERYMITIGATEDRANGECOUNT
 - DXGKARG_QUERYMITIGATEDRANGECOUNT
 - dispmprt/DXGKARG_QUERYMITIGATEDRANGECOUNT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKARG_QUERYMITIGATEDRANGECOUNT
 - PDXGKARG_QUERYMITIGATEDRANGECOUNT
 - DXGKARG_QUERYMITIGATEDRANGECOUNT
product:
 - Windows
dev_langs:
 - c++
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

