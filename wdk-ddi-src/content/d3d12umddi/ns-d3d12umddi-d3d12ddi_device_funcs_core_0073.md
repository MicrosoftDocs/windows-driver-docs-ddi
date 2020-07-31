---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_CORE_0073
title: D3D12DDI_DEVICE_FUNCS_CORE_0073
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
ms.assetid: 937ef7c9-9922-4f64-959d-4d3dd65460e0
tech.root: display
description: Core device functions available in D3D12 Release 7, Build rev 3.
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
req.typenames: D3D12DDI_DEVICE_FUNCS_CORE_0073
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_DEVICE_FUNCS_CORE_0073
f1_keywords:
 - d3d12umddi//D3D12DDI_DEVICE_FUNCS_CORE_0073
 - D3D12DDI_DEVICE_FUNCS_CORE_0073
dev_langs:
 - c++
---

## -description

Core device functions available in D3D12 Release 7, Build rev 3.

## -struct-fields

### -field pfnCheckFormatSupport

Check format support.

### -field pfnCheckMultisampleQualityLevels

Check multi sample quality levels.

### -field pfnGetMipPacking

Get MIP packing.

### -field pfnCalcPrivateElementLayoutSize

Calculate private element layout size.

### -field pfnCreateElementLayout

Create element layout.

### -field pfnDestroyElementLayout

Destroy element layout.

### -field pfnCalcPrivateBlendStateSize

Calculate private blend state size.

### -field pfnCreateBlendState

Create blend state.

### -field pfnDestroyBlendState

Destroy blend state.

### -field pfnCalcPrivateDepthStencilStateSize

Calculate private depth stencil state size.

### -field pfnCreateDepthStencilState

Create depth stencil state.

### -field pfnDestroyDepthStencilState

Destroy depth stencil state.

### -field pfnCalcPrivateRasterizerStateSize

Calculate private rasterizer state size.

### -field pfnCreateRasterizerState

Create rasterizer state.

### -field pfnDestroyRasterizerState

Destroy rasterizer state.

### -field pfnCalcPrivateShaderSize

Calculate private shader size.

### -field pfnCreateVertexShader

Create vertex shader.

### -field pfnCreatePixelShader

Create pixel shader.

### -field pfnCreateGeometryShader

Create geometry shader.

### -field pfnCreateComputeShader

Create compute shader.

### -field pfnCalcPrivateGeometryShaderWithStreamOutput

Calculate private geometry shader with stream output.

### -field pfnCreateGeometryShaderWithStreamOutput

Create geometry shader with stream output.

### -field pfnCalcPrivateTessellationShaderSize

Calculate private tessellation shader size.

### -field pfnCreateHullShader

Create hull shader.

### -field pfnCreateDomainShader

Create domain shader.

### -field pfnDestroyShader

Destroy shader.

### -field pfnCalcPrivateCommandQueueSize

Calculate private command queue size.

### -field pfnCreateCommandQueue

Create command queue.

### -field pfnDestroyCommandQueue

Destroy command queue.

### -field pfnCalcPrivateCommandPoolSize

Calculate private command pool size.

### -field pfnCreateCommandPool

Create command pool.

### -field pfnDestroyCommandPool

Destroy command pool.

### -field pfnResetCommandPool

Reset command pool.

### -field pfnCalcPrivatePipelineStateSize

Calculate private pipeline state size.

### -field pfnCreatePipelineState

Create pipeline state.

### -field pfnDestroyPipelineState

Destroy pipeline state.

### -field pfnCalcPrivateCommandListSize

Calculate private command list size.

### -field pfnCreateCommandList

Create command list.

### -field pfnDestroyCommandList

Destroy command list.

### -field pfnCalcPrivateFenceSize

Calculate private fence size.

### -field pfnCreateFence

Create fence.

### -field pfnDestroyFence

Destroy fence.

### -field pfnCalcPrivateDescriptorHeapSize

Calculate private descriptor heap size.

### -field pfnCreateDescriptorHeap

Create descriptor heap.

### -field pfnDestroyDescriptorHeap

Destroy descriptor heap.

### -field pfnGetDescriptorSizeInBytes

Get descriptor size in bytes.

### -field pfnGetCPUDescriptorHandleForHeapStart

Get CPU descriptor handle for heap start.

### -field pfnGetGPUDescriptorHandleForHeapStart

Get GPU descriptor handle for heap start.

### -field pfnCreateShaderResourceView

Create shader resource view.

### -field pfnCreateConstantBufferView

Create constant buffer view.

### -field pfnCreateSampler

Create sampler.

### -field pfnCreateUnorderedAccessView

Create unordered access view.

### -field pfnCreateRenderTargetView

Create render target view.

### -field pfnCreateDepthStencilView

Create depth stencil view.

### -field pfnCalcPrivateRootSignatureSize

Calculate private root signature size.

### -field pfnCreateRootSignature

Create root signature.

### -field pfnDestroyRootSignature

Destroy root signature.

### -field pfnMapHeap

Map heap.

### -field pfnUnmapHeap

Unmap heap.

### -field pfnCalcPrivateHeapAndResourceSizes

Calculate private heap and resource sizes.

### -field pfnCreateHeapAndResource

Create heap and resource.

### -field pfnDestroyHeapAndResource

Destroy heap and resource.

### -field pfnMakeResident

Make resident.

### -field pfnEvict

Evict.

### -field pfnCalcPrivateOpenedHeapAndResourceSizes

Calculate private opened heap and resource sizes.

### -field pfnOpenHeapAndResource

Open heap and resource.

### -field pfnCopyDescriptors

Copy descriptors.

### -field pfnCopyDescriptorsSimple

Copy descriptors sample.

### -field pfnCalcPrivateQueryHeapSize

Calculate private query heap size.

### -field pfnCreateQueryHeap

Create query heap.

### -field pfnDestroyQueryHeap

Destroy query heap.

### -field pfnCalcPrivateCommandSignatureSize

Calculate private command signature size.

### -field pfnCreateCommandSignature

Create command signature.

### -field pfnDestroyCommandSignature

Destroy command signature.

### -field pfnCheckResourceVirtualAddress

Check resource virtual address.

### -field pfnCheckResourceAllocationInfo

Check resource allocation info.

### -field pfnCheckSubresourceInfo

Check subresource info.

### -field pfnCheckExistingResourceAllocationInfo

Check existing resource allocation info.

### -field pfnOfferResources

Offer resources.

### -field pfnReclaimResources

Reclaim resources.

### -field pfnGetImplicitPhysicalAdapterMask

Get implicit physical adapter mask.

### -field pfnGetPresentPrivateDriverDataSize

Get present private driver data size.

### -field pfnQueryNodeMap

Query node map.

### -field pfnRetrieveShaderComment

Retrieve shader comment.

### -field pfnCheckResourceAllocationHandle

Check resource allocation handle.

### -field pfnCalcPrivatePipelineLibrarySize

Calculate private pipeline library size.

### -field pfnCreatePipelineLibrary

Create pipeline library.

### -field pfnDestroyPipelineLibrary

Destroy pipeline library.

### -field pfnAddPipelineStateToLibrary

Add pipeline state to library.

### -field pfnCalcSerializedLibrarySize

Calculate serialized library size.

### -field pfnSerializeLibrary

Serialize library.

### -field pfnGetDebugAllocationInfo

Get debug allocation info.

### -field pfnCalcPrivateCommandRecorderSize

Calculate private command recorder size.

### -field pfnCreateCommandRecorder

Create command recorder.

### -field pfnDestroyCommandRecorder

Destroy command recorder.

### -field pfnCommandRecorderSetCommandPoolAsTarget

Set the command pool as target for the command recorder.

### -field pfnCalcPrivateSchedulingGroupSize

Calculate private scheduling group size.

### -field pfnCreateSchedulingGroup

Create scheduling group.

### -field pfnDestroySchedulingGroup

Destroy scheduling group.

### -field pfnEnumerateMetaCommands

Enumerate meta-commands.

### -field pfnEnumerateMetaCommandParameters

Enumerate meta-command parameters.

### -field pfnCalcPrivateMetaCommandSize

Calculate private meta-command size.

### -field pfnCreateMetaCommand

Create meta-command.

### -field pfnDestroyMetaCommand

Destroy meta-command.

### -field pfnGetMetaCommandRequiredParameterInfo

Get required meta-command parameter info.

### -field pfnCalcPrivateStateObjectSize

Calculate private state object size.

### -field pfnCreateStateObject

Create state object.

### -field pfnDestroyStateObject

Destroy state object.

### -field pfnGetRaytracingAccelerationStructurePrebuildInfo

Get ray tracing acceleration structure prebuild info.

### -field pfnCheckDriverMatchingIdentifier

Check driver matching identifier.

### -field pfnGetShaderIdentifier

Get shader identifier.

### -field pfnGetShaderStackSize

Get shader stack size.

### -field pfnGetPipelineStackSize

Get pipeline stack size.

### -field pfnSetPipelineStackSize

Set pipeline stack size.

### -field pfnSetBackgroundProcessingMode

Sets the background processing mode.

### -field pfnCalcPrivateAddToStateObjectSize

Calculate private add to state object size. See the [DirectX Raytracing (DXR) Functional Spec](https://microsoft.github.io/DirectX-Specs/d3d/Raytracing.html) for more information.

### -field pfnAddToStateObject

Add to state object. See the [DirectX Raytracing (DXR) Functional Spec](https://microsoft.github.io/DirectX-Specs/d3d/Raytracing.html) for more information.

### -field pfnCreateSamplerFeedbackUnorderedAccessView

Create sampler feedback unordered access view. See the [D3D Sampler Feedback Specification](https://microsoft.github.io/DirectX-Specs/d3d/SamplerFeedback.html) for more information.

## -remarks

## -see-also
