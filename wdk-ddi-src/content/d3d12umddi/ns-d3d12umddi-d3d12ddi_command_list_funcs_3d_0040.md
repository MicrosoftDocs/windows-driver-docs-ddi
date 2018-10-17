---
UID: NS:d3d12umddi.D3D12DDI_COMMAND_LIST_FUNCS_3D_0040
title: D3D12DDI_COMMAND_LIST_FUNCS_3D_0040
author: windows-driver-content
description: The command list functions for 3D.
ms.assetid: e2a303e2-7780-4feb-8a65-4535cee8a41a
ms.date:
ms.topic: struct
ms.keywords: D3D12DDI_COMMAND_LIST_FUNCS_3D_0040, D3D12DDI_COMMAND_LIST_FUNCS_3D_0040,
req.header: d3d12umddi.h
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
req.typenames: D3D12DDI_COMMAND_LIST_FUNCS_3D_0040
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3d12umddi.h
api_name:
-	D3D12DDI_COMMAND_LIST_FUNCS_3D_0040
product: 
- Windows
targetos: Windows
tech.root: display
---

# D3D12DDI_COMMAND_LIST_FUNCS_3D_0040 structure

## -description

The command list functions for 3D.

## -struct-fields

### -field pfnCloseCommandList

Close the command list.

### -field pfnResetCommandList

Reset the command list.

### -field pfnDrawInstanced

Draw instanced.

### -field pfnDrawIndexedInstanced

Draw indexed instanced.

### -field pfnDispatch

Dispatched.

### -field pfnClearUnorderedAccessViewUint

Clear unordered access view unit.

### -field pfnClearUnorderedAccessViewFloat

Clear unordered access view float.

### -field pfnClearRenderTargetView

Clear render target view.

### -field pfnClearDepthStencilView

Clear depth stencil view.

### -field pfnDiscardResource

Discard resource.

### -field pfnCopyTextureRegion

Copy texture region.

### -field pfnResourceCopy

Copy resource.

### -field pfnCopyTiles

Copy tiles.

### -field pfnCopyBufferRegion

Copy buffer region.

### -field pfnResourceResolveSubresource

Resource resolve subresource.

### -field pfnExecuteBundle

Execute bundle.

### -field pfnExecuteIndirect

Execute indirect.

### -field pfnResourceBarrier

Resource barrier.

### -field pfnBlt

Blt.

### -field pfnPresent

Present.

### -field pfnBeginQuery

Begin query.


### -field pfnEndQuery

End query.


### -field pfnResolveQueryData

Resolve query data.


### -field pfnSetPredication

Set predication.


### -field pfnIaSetTopology

Set topology


### -field pfnRsSetViewports

Set view ports.


### -field pfnRsSetScissorRects

Set scissor rectangles.


### -field pfnOmSetBlendFactor

Set blend factor.


### -field pfnOmSetStencilRef

Set stencil reference.


### -field pfnSetPipelineState

Set pipeline state.


### -field pfnSetDescriptorHeaps

Set descriptor heaps.


### -field pfnSetComputeRootSignature

Set compute root signature.


### -field pfnSetGraphicsRootSignature

Set graphics root signature.


### -field pfnSetComputeRootDescriptorTable

Set compute root descriptor table.


### -field pfnSetGraphicsRootDescriptorTable

Set graphics root descriptor table.


### -field pfnSetComputeRoot32BitConstant

Set compute root 32-bit constant.


### -field pfnSetGraphicsRoot32BitConstant

Set graphics root 32-bit constant.


### -field pfnSetComputeRoot32BitConstants

Set compute root 32-bit constants.


### -field pfnSetGraphicsRoot32BitConstants

Set graphics root 32-bit constants.


### -field pfnSetComputeRootConstantBufferView

Set compute root constant buffer view.


### -field pfnSetGraphicsRootConstantBufferView

Set graphics root constant buffer view.


### -field pfnSetComputeRootShaderResourceView

Set compute root shader resource view.


### -field pfnSetGraphicsRootShaderResourceView

Set graphics root shader resource view.


### -field pfnSetComputeRootUnorderedAccessView

Set compute root unordered access view.


### -field pfnSetGraphicsRootUnorderedAccessView

Set graphics root unordered access view.


### -field pfnIASetIndexBuffer

Set index buffer.


### -field pfnIASetVertexBuffers

Set vertex buffers.


### -field pfnSOSetTargets

Set targets.


### -field pfnOMSetRenderTargets

Set render targets.


### -field pfnSetMarker

Set marker.


### -field pfnClearRootArguments

Clear root arguments.


### -field pfnAtomicCopyBufferRegion

Atomic copy buffer region.


### -field pfnOMSetDepthBounds

Set depth bounds.


### -field pfnSetSamplePositions

Set sample positions.


### -field pfnResourceResolveSubresourceRegion

Resource resolve subresource region.


### -field pfnSetProtectedResourceSession

Set protected resource session.


### -field pfnWriteBufferImmediate

Write buffer immediate.


### -field pfnSetViewInstanceMask

Set view instance mask.
