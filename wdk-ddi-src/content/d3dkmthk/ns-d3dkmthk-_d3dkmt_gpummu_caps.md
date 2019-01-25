---
UID: NS:d3dkmthk._D3DKMT_GPUMMU_CAPS
title: _D3DKMT_GPUMMU_CAPS (d3dkmthk.h)
description: Used to get GPU memory management unit capabilities.
ms.assetid: b341990c-5676-4da7-b70a-842e907c1c6e
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _D3DKMT_GPUMMU_CAPS, D3DKMT_GPUMMU_CAPS, 
req.header: d3dkmthk.h
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
req.typenames: D3DKMT_GPUMMU_CAPS
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dkmthk.h
api_name: 
-	_D3DKMT_GPUMMU_CAPS
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# _D3DKMT_GPUMMU_CAPS structure

## -description

Used to get GPU memory management unit capabilities.

## -struct-fields

### -field Flags

Flags to indicate the type of capabilities.

### -field Flags.ReadOnlyMemorySupported

Read-only memory is supported.

### -field Flags.NoExecuteMemorySupported

No execute memory is supported.

### -field Flags.CacheCoherentMemorySupported

Cache coherent memory is supported.

### -field Flags.Reserved

Reserved for system use.

### -field Flags.Value
 
### -field VirtualAddressBitCount
 
The virtual address bit count.

## -remarks

## -see-also
