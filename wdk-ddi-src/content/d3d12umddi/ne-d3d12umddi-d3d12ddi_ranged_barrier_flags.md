---
UID: NE:d3d12umddi.D3D12DDI_RANGED_BARRIER_FLAGS
tech.root: display
title: D3D12DDI_RANGED_BARRIER_FLAGS
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the D3D12DDI_RANGED_BARRIER_FLAGS enumeration.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_RANGED_BARRIER_FLAGS
f1_keywords:
 - D3D12DDI_RANGED_BARRIER_FLAGS
 - d3d12umddi/D3D12DDI_RANGED_BARRIER_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_RANGED_BARRIER_FLAGS
---

## -description

The **D3D12DDI_RANGED_BARRIER_FLAGS** enumeration specifies flags for resource barriers.

## -enum-fields

### -field D3D12DDI_RANGED_BARRIER_FLAG_NONE:0

No flags are specified.

### -field D3D12DDI_RANGED_BARRIER_FLAG_ATOMIC_COPY:0x1

The barrier is associated with a parameter of an atomic copy operation.

## -remarks

See [Enhanced Barriers](/windows-hardware/drivers/display/enhanced-barriers) for general information.

## -see-also

[**D3D12DDI_RANGED_BARRIER_0088**]*(ns-d3d12umddi-d3d12ddi_ranged_barrier_0088.md)
