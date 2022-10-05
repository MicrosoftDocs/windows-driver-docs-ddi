---
UID: NS:d3d12umddi.D3D12DDIARG_BARRIER_0088
tech.root: display
title: D3D12DDIARG_BARRIER_0088
ms.date: 09/29/2022
targetos: Windows
description: Learn more about the D3D12DDIARG_BARRIER_0088 structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDIARG_BARRIER_0088
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_BARRIER_0088
f1_keywords:
 - D3D12DDIARG_BARRIER_0088
 - d3d12umddi/D3D12DDIARG_BARRIER_0088
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDIARG_BARRIER_0088
---

## -description

The **D3D12DDIARG_BARRIER_0088** structure contains the enhanced barrier parameters for the [**PFND3D12DDI_BARRIER_0088**](nc-d3d12umddi-pfnd3d12ddi_barrier_0088.md) callback function.

## -struct-fields

### -field Type

A [**D3D12DDI_BARRIER_TYPE**](ne-d3d12umddi-d3d12ddi_barrier_type.md) value that identifies the type of enhanced barrier. This member determines which barrier type to use in the union below.

### -field GlobalBarrier

A [**D3D12DDI_GLOBAL_BARRIER_0088**](ns-d3d12umddi-d3d12ddi_global_barrier_0088.md) structure that describes the global barrier. Use this structure when **Type** is **D3D12DDI_BARRIER_TYPE_GLOBAL**.

### -field TextureBarrier

A [**D3D12DDI_TEXTURE_BARRIER_0088**](ns-d3d12umddi-d3d12ddi_texture_barrier_0088.md) structure that describes a texture barrier. Use this structure when **Type** is **D3D12DDI_BARRIER_TYPE_TEXTURE**.

### -field BufferBarrier

A [**D3D12DDI_BUFFER_BARRIER_0088**](ns-d3d12umddi-d3d12ddi_buffer_barrier_0088.md) structure that describes a buffer barrier. Use this structure when **Type** is **D3D12DDI_BARRIER_TYPE_BUFFER**.

### -field RangedBarrier

A [**D3D12DDI_RANGED_BARRIER_0088**](ns-d3d12umddi-d3d12ddi_ranged_barrier_0088.md) structure that describes a resource ranged barrier. Use this structure when **Type** is **D3D12DDI_BARRIER_TYPE_RANGED**.

## -remarks

See [Enhanced Barriers](/windows-hardware/drivers/display/enhanced-barriers) for general information.

## -see-also

[**PFND3D12DDI_BARRIER_0088**](nc-d3d12umddi-pfnd3d12ddi_barrier_0088.md)
