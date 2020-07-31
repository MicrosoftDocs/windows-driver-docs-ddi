---
UID: NS:dispmprt._DXGKARG_GETVIRTUALGPUINFO
title: _DXGKARG_GETVIRTUALGPUINFO
author: windows-driver-content
description: Arguments used to get virtual GPU info.
tech.root: display
ms.assetid: e6b55c00-3abf-42fa-8dfc-8bd5e5731362
ms.author: windowsdriverdev
ms.date: 04/04/2019 
keywords: ["_DXGKARG_GETVIRTUALGPUINFO structure"]
f1_keywords:
 - "dispmprt/_DXGKARG_GETVIRTUALGPUINFO"
 - "_DXGKARG_GETVIRTUALGPUINFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARG_GETVIRTUALGPUINFO, DXGKARG_GETVIRTUALGPUINFO, *PDXGKARG_GETVIRTUALGPUINFO, 
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
req.typenames: DXGKARG_GETVIRTUALGPUINFO, *PDXGKARG_GETVIRTUALGPUINFO
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - dispmprt.h
api_name: 
 - _DXGKARG_GETVIRTUALGPUINFO
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# _DXGKARG_GETVIRTUALGPUINFO structure

## -description

Arguments used to get virtual GPU info.

## -struct-fields

### -field PartitionId

An index (from 0 to maximum supported vGPU minus one) for the vGPU partition.

### -field Capability
 
The array of capability values, which include Memory, Encode, Decode and Compute. A minimum, maximum and optimal values are specified for each capability. When the vGPU is running, each capability cannot be lower than MinValue and more than MaxValue. The driver could assign the current capability value based in the physical GPU load.

## -remarks

## -see-also
