---
UID: NS:dispmprt._DXGKARG_GETDEVICELOCATION
title: _DXGKARG_GETDEVICELOCATION
description: Arguments used to get the location of a Virtual Function on the PCI bus relative to the root partition.
tech.root: display
ms.date: 04/04/2019
keywords: ["DXGKARG_GETDEVICELOCATION structure"]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARG_GETDEVICELOCATION, DXGKARG_GETDEVICELOCATION, *PDXGKARG_GETDEVICELOCATION,
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
req.typenames: DXGKARG_GETDEVICELOCATION, *PDXGKARG_GETDEVICELOCATION
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _DXGKARG_GETDEVICELOCATION
 - dispmprt/_DXGKARG_GETDEVICELOCATION
 - PDXGKARG_GETDEVICELOCATION
 - dispmprt/PDXGKARG_GETDEVICELOCATION
 - DXGKARG_GETDEVICELOCATION
 - dispmprt/DXGKARG_GETDEVICELOCATION
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKARG_GETDEVICELOCATION
product:
 - Windows
dev_langs:
 - c++
---

# _DXGKARG_GETDEVICELOCATION structure


## -description

Arguments used to get the location of a Virtual Function on the PCI bus relative to the root partition.

## -struct-fields

### -field VirtualFunctionIndex

Zero-based offset of the Virtual Function from the first VF exposed by this Physical Function.

### -field SegmentNumber

To be filled in with the segment number of this function.

### -field BusNumber

To be filled in with the bus number of this function.

### -field FunctionNumber

 
To be filled in with the function number of this function.

## -remarks

## -see-also

