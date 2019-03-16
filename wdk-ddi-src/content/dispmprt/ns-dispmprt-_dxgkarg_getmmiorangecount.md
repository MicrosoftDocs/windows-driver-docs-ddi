---
UID: NS:dispmprt._DXGKARG_GETMMIORANGECOUNT
title: _DXGKARG_GETMMIORANGECOUNT (dispmprt.h)
description: Arguments used to get the memory mapped input output range count.
ms.assetid: 0949fc6e-b58f-4e20-83dd-c8a8df68059b
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _DXGKARG_GETMMIORANGECOUNT, DXGKARG_GETMMIORANGECOUNT, *PDXGKARG_GETMMIORANGECOUNT, 
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
req.typenames: DXGKARG_GETMMIORANGECOUNT, *PDXGKARG_GETMMIORANGECOUNT
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- dispmprt.h
api_name: 
- _DXGKARG_GETMMIORANGECOUNT
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# _DXGKARG_GETMMIORANGECOUNT structure

## -description

Arguments used to get the memory mapped input output range count.

## -struct-fields

### -field VirtualFunctionIndex

The particular Virtual function to query.

### -field RangeCount
 
The array of ranges, one for each of the virtual devices MMIO Bars.

## -remarks

## -see-also
