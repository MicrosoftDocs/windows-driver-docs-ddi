---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_CORE_0088
tech.root: display
title: D3D12DDI_DEVICE_FUNCS_CORE_0088
ms.date: 02/24/2023
targetos: Windows
description: Learn more about the D3D12DDI_DEVICE_FUNCS_CORE_0088 structure.
prerelease: false
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
req.typenames: D3D12DDI_DEVICE_FUNCS_CORE_0088
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_DEVICE_FUNCS_CORE_0088
f1_keywords:
 - D3D12DDI_DEVICE_FUNCS_CORE_0088
 - d3d12umddi/D3D12DDI_DEVICE_FUNCS_CORE_0088
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_DEVICE_FUNCS_CORE_0088
---

## -description

The **D3D12DDI_DEVICE_FUNCS_CORE_0088** structure contains the core device functionality available in D3D12 Release 8, Build rev 8. The user-mode driver returns its function pointers in this structure when [**PFND3D12DDI_FILLDDITTABLE**](nc-d3d12umddi-pfnd3d12ddi_fillddittable.md) is called with a [**D3D12DDI_TABLE_TYPE**](ne-d3d12umddi-d3d12ddi_table_type.md) of **D3D12DDI_TABLE_TYPE_DEVICE_CORE**.

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

Pointer to the function to create a domain shader.

### -field pfnDestroyShader

Pointer to the function to destroy a shader.

### -field pfnCalcPrivateCommandQueueSize

Pointer to the function to calculate private command queue size.

### -field pfnCreateCommandQueue

Pointer to the function to create a command queue.

### -field pfnDestroyCommandQueue

Pointer to the function to destroy a command queue.

### -field pfnCalcPrivateCommandPoolSize

Pointer to the function to calculate private command pool size.

### -field pfnCreateCommandPool

Pointer to the function to create a command pool.

### -field pfnDestroyCommandPool

Pointer to the function to destroy a command pool.

### -field pfnResetCommandPool

Pointer to the function to reset a command pool.

### -field pfnCalcPrivatePipelineStateSize

Pointer to the function to calculate private pipeline state size.

### -field pfnCreatePipelineState

Pointer to the function to create pipeline state.

### -field pfnDestroyPipelineState

Pointer to the function to destroy pipeline state.

### -field pfnCalcPrivateCommandListSize

Pointer to the function to calculate the private command list size.

### -field pfnCreateCommandList

Pointer to the function to create a command list.

### -field pfnDestroyCommandList

Pointer to the function to destroy a command list.

### -field pfnCalcPrivateFenceSize

Pointer to the function to calculate private fence size.

### -field pfnCreateFence

Pointer to the function to create a fence.

### -field pfnDestroyFence

Pointer to the function to destroy a fence.

### -field pfnCalcPrivateDescriptorHeapSize

Pointer to the function to calculate private descriptor heap size.

### -field pfnCreateDescriptorHeap

Pointer to the function to create a descriptor heap.

### -field pfnDestroyDescriptorHeap

Pointer to the function to destroy a descriptor heap.

### -field pfnGetDescriptorSizeInBytes

Pointer to the function to get a descriptor's size in bytes.

### -field pfnGetCPUDescriptorHandleForHeapStart

Pointer to the function to get a CPU descriptor handle for heap start.

### -field pfnGetGPUDescriptorHandleForHeapStart

Pointer to the function to get a GPU descriptor handle for heap start.

### -field pfnCreateShaderResourceView

Pointer to the function to create a shader resource view.

### -field pfnCreateConstantBufferView

Pointer to the function to create a constant buffer view.

### -field pfnCreateSampler

Pointer to the function to create a sampler.

### -field pfnCreateUnorderedAccessView

Pointer to the function to create a unordered access view.

### -field pfnCreateRenderTargetView

Pointer to the function to create a render target view.

### -field pfnCreateDepthStencilView

Pointer to the function to create a depth stencil view.

### -field pfnCalcPrivateRootSignatureSize

Pointer to the function to calculate a private root signature size.

### -field pfnCreateRootSignature

Pointer to the function to create a root signature.

### -field pfnDestroyRootSignature

Pointer to the function to destroy a root signature.

### -field pfnMapHeap

Pointer to the function to map a heap.

### -field pfnUnmapHeap

Pointer to the function to unmap a heap.

### -field pfnCalcPrivateHeapAndResourceSizes

Pointer to the function to calculate private heap and resource sizes.

### -field pfnCreateHeapAndResource

Pointer to the function to create a heap and resource.

### -field pfnDestroyHeapAndResource

Pointer to the function to destroy a heap and resource.

### -field pfnMakeResident

Pointer to the function to make resident.

### -field pfnEvict

Pointer to the function to evict.

### -field pfnCalcPrivateOpenedHeapAndResourceSizes

Pointer to the function to calculate private opened heap and resource sizes.

### -field pfnOpenHeapAndResource

Pointer to the function to open heap and resource.

### -field pfnCopyDescriptors

Pointer to the function to copy descriptors.

### -field pfnCopyDescriptorsSimple

Pointer to the function to copy descriptors sample.

### -field pfnCalcPrivateQueryHeapSize

Pointer to the function to calculate private query heap size.

### -field pfnCreateQueryHeap

Pointer to the function to create query heap.

### -field pfnDestroyQueryHeap

Pointer to the function to destroy query heap.

### -field pfnCalcPrivateCommandSignatureSize

Pointer to the function to calculate private command signature size.

### -field pfnCreateCommandSignature

Pointer to the function to create command signature.

### -field pfnDestroyCommandSignature

Pointer to the function to destroy command signature.

### -field pfnCheckResourceVirtualAddress

Pointer to the function to check resource virtual address.

### -field pfnCheckResourceAllocationInfo

Pointer to the function to check resource allocation info.

### -field pfnCheckSubresourceInfo

Pointer to the function to check subresource info.

### -field pfnCheckExistingResourceAllocationInfo

Pointer to the function to check existing resource allocation info.

### -field pfnOfferResources

Offer resources.

### -field pfnReclaimResources

Pointer to the function to reclaim resources.

### -field pfnGetImplicitPhysicalAdapterMask

Pointer to the function to get implicit physical adapter mask.

### -field pfnGetPresentPrivateDriverDataSize

Pointer to the function to get present private driver data size.

### -field pfnQueryNodeMap

Pointer to the function to query a node map.

### -field pfnRetrieveShaderComment

Pointer to the function to retrieve a shader comment.

### -field pfnCheckResourceAllocationHandle

Pointer to the function to check a resource allocation handle.

### -field pfnCalcPrivatePipelineLibrarySize

Pointer to the function to calculate private pipeline library size.

### -field pfnCreatePipelineLibrary

Pointer to the function to create a pipeline library.

### -field pfnDestroyPipelineLibrary

Pointer to the function to destroy a pipeline library.

### -field pfnAddPipelineStateToLibrary

Pointer to the function to add pipeline state to library.

### -field pfnCalcSerializedLibrarySize

Pointer to the function to calculate serialized library size.

### -field pfnSerializeLibrary

Pointer to the function to serialize a library.

### -field pfnGetDebugAllocationInfo

Pointer to the function to get debug allocation info.

### -field pfnCalcPrivateCommandRecorderSize

Pointer to the function to calculate private command recorder size.

### -field pfnCreateCommandRecorder

Pointer to the function to create a command recorder.

### -field pfnDestroyCommandRecorder

Pointer to the function to destroy a command recorder.

### -field pfnCommandRecorderSetCommandPoolAsTarget

Pointer to the function to set the command pool as target for the command recorder.

### -field pfnCalcPrivateSchedulingGroupSize

Pointer to the function to calculate private scheduling group size.

### -field pfnCreateSchedulingGroup

Pointer to the function to create a scheduling group.

### -field pfnDestroySchedulingGroup

Pointer to the function to destroy a scheduling group.

### -field pfnEnumerateMetaCommands

Pointer to the function to enumerate meta-commands.

### -field pfnEnumerateMetaCommandParameters

Pointer to the function to enumerate meta-command parameters.

### -field pfnCalcPrivateMetaCommandSize

Pointer to the function to calculate private meta-command size.

### -field pfnCreateMetaCommand

Pointer to the function to create a meta-command.

### -field pfnDestroyMetaCommand

Pointer to the function to destroy a meta-command.

### -field pfnGetMetaCommandRequiredParameterInfo

Pointer to the function to get required meta-command parameter info.

### -field pfnCalcPrivateStateObjectSize

Pointer to the function to calculate private state object size.

### -field pfnCreateStateObject

Pointer to the function to create a state object.

### -field pfnDestroyStateObject

Pointer to the function to destroy a state object.

### -field pfnGetRaytracingAccelerationStructurePrebuildInfo

Pointer to the function to get ray tracing acceleration structure prebuild info.

### -field pfnCheckDriverMatchingIdentifier

Pointer to the function to check driver matching identifier.

### -field pfnGetShaderIdentifier

Pointer to the function to get a shader identifier.

### -field pfnGetShaderStackSize

Pointer to the function to get a shader stack size.

### -field pfnGetPipelineStackSize

Pointer to the function to get a pipeline stack size.

### -field pfnSetPipelineStackSize

Pointer to the function to set pipeline stack size.

### -field pfnSetBackgroundProcessingMode

Pointer to the function to set the background processing mode.

### -field pfnCalcPrivateAddToStateObjectSize

Pointer to the function to calculate private add to state object size. See the [DirectX Raytracing (DXR) Functional Spec](https://microsoft.github.io/DirectX-Specs/d3d/Raytracing.html) for more information.

### -field pfnAddToStateObject

Pointer to the function to add to state object. See the [DirectX Raytracing (DXR) Functional Spec](https://microsoft.github.io/DirectX-Specs/d3d/Raytracing.html) for more information.

### -field pfnCreateSamplerFeedbackUnorderedAccessView

Pointer to the function to create a sampler feedback unordered access view. See the [D3D Sampler Feedback Specification](https://microsoft.github.io/DirectX-Specs/d3d/SamplerFeedback.html) for more information.

### -field pfnCreateAmplificationShader

Pointer to the function to create an amplification shader. See the [Mesh Shader Specification](https://microsoft.github.io/DirectX-Specs/d3d/MeshShader.html) for more information.

### -field pfnCreateMeshShader

Pointer to the function to create a mesh shader. See the [Mesh Shader Specification](https://microsoft.github.io/DirectX-Specs/d3d/MeshShader.html) for more information.

### -field pfnCalcPrivateMeshShaderSize

Pointer to the function to calculate private mesh shader size. See the [Mesh Shader Specification](https://microsoft.github.io/DirectX-Specs/d3d/MeshShader.html) for more information.

### -field pfnImplicitShaderCacheControl

Pointer to the function for implicit shader cache control. See the [D3D12 Shader Cache APIs specification](https://microsoft.github.io/DirectX-Specs/d3d/ShaderCache.html) for more information.

## -see-also

[**D3D12DDI_TABLE_TYPE**](ne-d3d12umddi-d3d12ddi_table_type.md)

[**PFND3D12DDI_FILLDDITTABLE**](nc-d3d12umddi-pfnd3d12ddi_fillddittable.md)
