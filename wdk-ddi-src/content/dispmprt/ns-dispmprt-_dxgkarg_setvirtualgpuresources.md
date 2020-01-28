---
UID: NS:dispmprt._DXGKARG_SETVIRTUALGPURESOURCES
title: _DXGKARG_SETVIRTUALGPURESOURCES
author: windows-driver-content
description: 
tech.root: display
ms.assetid: 1adf321c-b791-4dee-a948-78bfd07a6d38
ms.author: windowsdriverdev
ms.date: 04/04/2019 
f1_keywords:
 - "dispmprt/_DXGKARG_SETVIRTUALGPURESOURCES"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARG_SETVIRTUALGPURESOURCES, DXGKARG_SETVIRTUALGPURESOURCES, *PDXGKARG_SETVIRTUALGPURESOURCES, 
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
req.typenames: DXGKARG_SETVIRTUALGPURESOURCES, *PDXGKARG_SETVIRTUALGPURESOURCES
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - dispmprt.h
api_name: 
 - _DXGKARG_SETVIRTUALGPURESOURCES
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# _DXGKARG_SETVIRTUALGPURESOURCES structure

## -description

Arguments used to set virtual GPU resources.

## -struct-fields

### -field PartitionId

An index (from 0 to maximum supported vGPU minus one) for the vGPU partition.

### -field NumMemoryAllocations

The number of memory allocations, assigned to the vGPU.

### -field MemoryInfo
 
The array of requested assigned memory allocations.

## -remarks

## -see-also
