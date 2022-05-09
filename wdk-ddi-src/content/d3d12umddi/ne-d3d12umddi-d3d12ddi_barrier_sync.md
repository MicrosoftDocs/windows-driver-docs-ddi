---
UID: NE:d3d12umddi.D3D12DDI_BARRIER_SYNC
tech.root: display
title: D3D12DDI_BARRIER_SYNC
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the D3D12DDI_BARRIER_SYNC enumeration.
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
 - D3D12DDI_BARRIER_SYNC
f1_keywords:
 - D3D12DDI_BARRIER_SYNC
 - d3d12umddi/D3D12DDI_BARRIER_SYNC
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_BARRIER_SYNC
---

## -description

## -enum-fields

### -field D3D12DDI_BARRIER_SYNC_NONE

Indicates synchronization is not needed either before or after a barrier. When used, **D3D12DDI_BARRIER_SYNC_NONE** must be the only bit set. See Remarks for details.

### -field D3D12DDI_BARRIER_SYNC_ALL

### -field D3D12DDI_BARRIER_SYNC_DRAW

### -field D3D12DDI_BARRIER_SYNC_INPUT_ASSEMBLER

### -field D3D12DDI_BARRIER_SYNC_VERTEX_SHADING

### -field D3D12DDI_BARRIER_SYNC_PIXEL_SHADING

### -field D3D12DDI_BARRIER_SYNC_DEPTH_STENCIL

### -field D3D12DDI_BARRIER_SYNC_RENDER_TARGET

### -field D3D12DDI_BARRIER_SYNC_COMPUTE_SHADING

### -field D3D12DDI_BARRIER_SYNC_RAYTRACING

### -field D3D12DDI_BARRIER_SYNC_COPY

### -field D3D12DDI_BARRIER_SYNC_RESOLVE

### -field D3D12DDI_BARRIER_SYNC_EXECUTE_INDIRECT

### -field D3D12DDI_BARRIER_SYNC_PREDICATION

### -field D3D12DDI_BARRIER_SYNC_ALL_SHADING

### -field D3D12DDI_BARRIER_SYNC_NON_PIXEL_SHADING

### -field D3D12DDI_BARRIER_SYNC_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO

### -field D3D12DDI_BARRIER_SYNC_VIDEO_DECODE

### -field D3D12DDI_BARRIER_SYNC_VIDEO_PROCESS

### -field D3D12DDI_BARRIER_SYNC_VIDEO_ENCODE

### -field D3D12DDI_BARRIER_SYNC_BUILD_RAYTRACING_ACCELERATION_STRUCTURE

### -field D3D12DDI_BARRIER_SYNC_COPY_RAYTRACING_ACCELERATION_STRUCTURE

### -field D3D12DDI_BARRIER_SYNC_SPLIT

## -remarks

If a barrier's **SyncBefore** value is **D3D12DDI_BARRIER_SYNC_NONE**, this implies that the corresponding subresources are not accessed *before* the barrier in the same [**PFND3D12DDI_EXECUTECOMMANDLISTS**](nc-d3d12umddi-pfnd3d12ddi_executecommandlists.md) scope, so **AccessBefore** must be **D3D12DDI_BARRIER_ACCESS_NO_ACCESS**. In this case, there must have been no preceding barriers or accesses made to that resource in the same ExecuteCommandLists scope.

A **SyncAfter** value of **D3D12DDI_BARRIER_SYNC_NONE** implies that the corresponding subresources are not accessed *after* the barrier in the same [**PFND3D12DDI_EXECUTECOMMANDLISTS**](nc-d3d12umddi-pfnd3d12ddi_executecommandlists.md) scope, so **AccessAfter** must be **D3D12DDI_BARRIER_ACCESS_NO_ACCESS**. In this case, there must be no subsequent barriers or accesses made afterwards to the associated resource in the same ExecuteCommandLists scope.

## -see-also

