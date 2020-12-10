---
UID: NS:d3dumddi._D3D12DDICB_OFFERALLOCATIONS
title: _D3D12DDICB_OFFERALLOCATIONS (d3dumddi.h)
description: The D3D12DDICB_OFFERALLOCATIONS structure is used to offer allocations.
ms.date: 10/19/2018
keywords: ["D3D12DDICB_OFFERALLOCATIONS structure"]
ms.keywords: _D3D12DDICB_OFFERALLOCATIONS, D3D12DDICB_OFFERALLOCATIONS,
req.header: d3dumddi.h
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
req.typenames: D3D12DDICB_OFFERALLOCATIONS
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3D12DDICB_OFFERALLOCATIONS
 - d3dumddi/_D3D12DDICB_OFFERALLOCATIONS
 - D3D12DDICB_OFFERALLOCATIONS
 - d3dumddi/D3D12DDICB_OFFERALLOCATIONS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3D12DDICB_OFFERALLOCATIONS
dev_langs:
 - c++
---

# _D3D12DDICB_OFFERALLOCATIONS structure


## -description

The D3D12DDICB_OFFERALLOCATIONS structure is used to offer allocations.

## -struct-fields

### -field NumAllocations

[in] The number of allocations in the HandleList array.

### -field HandleList

[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to the allocations.

### -field Priority

The allocation priority.

## -remarks

## -see-also

