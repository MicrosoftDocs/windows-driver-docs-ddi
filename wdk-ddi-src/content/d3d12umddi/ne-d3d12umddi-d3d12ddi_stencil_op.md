---
UID: NE:d3d12umddi.D3D12DDI_STENCIL_OP
title: D3D12DDI_STENCIL_OP (d3d12umddi.h)
description: The D3D12DDI_STENCIL_OP enumeration type contains values that identify operations on stencil buffers.
ms.assetid: 984415f8-a577-4344-aedb-161155f113af
ms.date: 10/19/2018
ms.topic: enum
ms.keywords: D3D12DDI_STENCIL_OP, D3D12DDI_STENCIL_OP, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3D12DDI_STENCIL_OP
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_STENCIL_OP
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDI_STENCIL_OP enumeration

## -description

The D3D12DDI_STENCIL_OP enumeration type contains values that identify operations on stencil buffers in a call to the driver's [CreateDepthStencilState](nc-d3d12umddi-pfnd3d12ddi_createdepthstencilstate_0003.md) function.

## -enum-fields

### -field D3D12DDI_STENCIL_OP_KEEP

Do not update the entry in the stencil buffer. D3D12DDI_STENCIL_OP_KEEP is the default value.

### -field D3D12DDI_STENCIL_OP_ZERO

Set the stencil-buffer entry to 0.

### -field D3D12DDI_STENCIL_OP_REPLACE

Replace the stencil-buffer entry with a reference value.

### -field D3D12DDI_STENCIL_OP_INCR_SAT

Increment the stencil-buffer entry, clamping to the maximum value.

### -field D3D12DDI_STENCIL_OP_DECR_SAT

Decrement the stencil-buffer entry, clamping to zero.

### -field D3D12DDI_STENCIL_OP_INVERT

Invert the bits in the stencil-buffer entry.

### -field D3D12DDI_STENCIL_OP_INCR

Increment the stencil-buffer entry, wrapping to zero if the new value exceeds the maximum value.

### -field D3D12DDI_STENCIL_OP_DECR 

Decrement the stencil-buffer entry, wrapping to the maximum value if the new value is less than zero.

## -remarks

## -see-also
