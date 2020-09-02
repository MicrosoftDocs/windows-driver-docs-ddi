---
UID: NS:d3d12umddi.D3D12DDI_COMMAND_LIST_FUNCS_3D_0074
title: D3D12DDI_COMMAND_LIST_FUNCS_3D_0074
ms.date: 03/24/2020
ms.topic: language-reference
ms.assetid: 0bd7af69-da02-4566-90d4-714ebf402b03
tech.root: display
targetos: Windows
description: The command list 3D functions for version Direct3D 12 Release 7, Build rev 4.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_COMMAND_LIST_FUNCS_3D_0074
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_COMMAND_LIST_FUNCS_3D_0074
f1_keywords:
 - D3D12DDI_COMMAND_LIST_FUNCS_3D_0074
 - d3d12umddi/D3D12DDI_COMMAND_LIST_FUNCS_3D_0074
dev_langs:
 - c++
---

## -description

The command list 3D functions for version Direct3D 12 Release 7, Build rev 4.

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

Dispatch.

### -field pfnClearUnorderedAccessViewUint

Clear the unordered access view of UINT values.

### -field pfnClearUnorderedAccessViewFloat

Clear the unordered access view of FLOAT values.

### -field pfnClearRenderTargetView

Clear the render target view.

### -field pfnClearDepthStencilView

Clear the depth stencil view.

### -field pfnDiscardResource

Discard resource.

### -field pfnCopyTextureRegion

Copy texture region.

### -field pfnResourceCopy

Resource copy.

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

Set topology.

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

### -field pfnInitializeMetaCommand

Initialize a meta-command.

### -field pfnExecuteMetaCommand

Execute a meta-command.

### -field pfnBuildRaytracingAccelerationStructure

Build a ray tracing acceleration structure.

### -field pfnEmitRaytracingAccelerationStructurePostbuildInfo

Emit ray tracing acceleration structure post build info.

### -field pfnCopyRaytracingAccelerationStructure

Copy ray tracing acceleration structure.

### -field pfnSetPipelineState1

Set pipeline state.

### -field pfnDispatchRays

Dispatch rays.

### -field pfnRSSetShadingRate

Sets the command-level shading rate and combiners.

### -field pfnRSSetShadingRateImage

Sets the screen space image.

### -field pfnDispatchMesh

Dispatch mesh. See the [D3D Sampler Feedback Specification](https://microsoft.github.io/DirectX-Specs/d3d/SamplerFeedback.html) for more information.

## -remarks

## -see-also

