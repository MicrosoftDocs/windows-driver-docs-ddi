---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_CORE_0108
tech.root: display
title: D3D12DDI_DEVICE_FUNCS_CORE_0108
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the D3D12DDI_DEVICE_FUNCS_CORE_0108 structure.
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
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_DEVICE_FUNCS_CORE_0108
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_DEVICE_FUNCS_CORE_0108
f1_keywords:
 - D3D12DDI_DEVICE_FUNCS_CORE_0108
 - d3d12umddi/D3D12DDI_DEVICE_FUNCS_CORE_0108
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_DEVICE_FUNCS_CORE_0108
---

# D3D12DDI_DEVICE_FUNCS_CORE_0108 structure (d3d12umddi.h)

## -description

The **D3D12DDI_DEVICE_FUNCS_CORE_0108** structure contains the core device functionality available in D3D12 Release 8, Build rev 108. The user-mode driver (UMD) returns its function pointers in this structure when its [**PFND3D12DDI_FILLDDITTABLE**](nc-d3d12umddi-pfnd3d12ddi_fillddittable.md) function is called with a [**D3D12DDI_TABLE_TYPE**](ne-d3d12umddi-d3d12ddi_table_type.md) of **D3D12DDI_TABLE_TYPE_DEVICE_CORE**.

## -struct-fields

### -field pfnCheckFormatSupport

Points to a function that checks the support of a particular format on the GPU.

### -field pfnCheckMultisampleQualityLevels

Points to a function that checks the available quality levels for multisample anti-aliasing with a given format and sample count.

### -field pfnGetMipPacking

Points to a function that retrieves information about how mips are packed in a resource.

### -field pfnCalcPrivateElementLayoutSize

Points to a function that calculates the size of the private element layout.

### -field pfnCreateElementLayout

Points to a function that creates an element layout.

### -field pfnDestroyElementLayout

Points to a function that destroys an element layout.

### -field pfnCalcPrivateBlendStateSize

Points to a function that calculates the size of the private blend state.

### -field pfnCreateBlendState

Points to a function that creates a blend state.

### -field pfnDestroyBlendState

Points to a function that destroys a blend state.

### -field pfnCalcPrivateDepthStencilStateSize

Points to a function that calculates the size of the private depth stencil state.

### -field pfnCreateDepthStencilState

Points to a function that creates a depth stencil state.

### -field pfnDestroyDepthStencilState

Points to a function that destroys a depth stencil state.

### -field pfnCalcPrivateRasterizerStateSize

Points to a function that calculates the size of the private rasterizer state.

### -field pfnCreateRasterizerState

Points to a function that creates a rasterizer state.

### -field pfnDestroyRasterizerState

Points to a function that destroys a rasterizer state.

### -field pfnCalcPrivateShaderSize

Points to a function that calculates the size of the private shader.

### -field pfnCreateVertexShader

Points to a function that creates a vertex shader.

### -field pfnCreatePixelShader

Points to a function that creates a pixel shader.

### -field pfnCreateGeometryShader

Points to a function that creates a geometry shader.

### -field pfnCreateComputeShader

Points to a function that creates a compute shader.

### -field pfnCalcPrivateGeometryShaderWithStreamOutput

Points to a function that calculates the size of a private geometry shader with stream output.

### -field pfnCreateGeometryShaderWithStreamOutput

Points to a function that creates a geometry shader with stream output.

### -field pfnCalcPrivateTessellationShaderSize

Points to a function that calculates the size of the private tessellation shader.

### -field pfnCreateHullShader

Points to a function that creates a hull shader.

### -field pfnCreateDomainShader

Points to a function that creates a domain shader.

### -field pfnDestroyShader

Points to a function that destroys a shader.

### -field pfnCalcPrivateCommandQueueSize

Points to a function that calculates the size of the private command queue.

### -field pfnCreateCommandQueue

Points to a function that creates a command queue.

### -field pfnDestroyCommandQueue

Points to a function that destroys a command queue.

### -field pfnCalcPrivateCommandPoolSize

Points to a function that calculates the size of the private command pool.

### -field pfnCreateCommandPool

Points to a function that creates a command pool.

### -field pfnDestroyCommandPool

Points to a function that destroys a command pool.

### -field pfnResetCommandPool

Points to a function that resets a command pool.

### -field pfnCalcPrivatePipelineStateSize

Points to a function that calculates the size of the private pipeline state.

### -field pfnCreatePipelineState

Points to a function that creates pipeline state.

### -field pfnDestroyPipelineState

Points to a function that destroys pipeline state.

### -field pfnCalcPrivateCommandListSize

Points to a function that calculates the private command list size.

### -field pfnCreateCommandList

Points to a function that creates a command list.

### -field pfnDestroyCommandList

Points to a function that destroys a command list.

### -field pfnCalcPrivateFenceSize

Points to a function that calculates a private fence size.

### -field pfnCreateFence

Points to a function that creates a fence.

### -field pfnDestroyFence

Points to a function that destroys a fence.

### -field pfnCalcPrivateDescriptorHeapSize

Points to a function that calculates private descriptor heap size.

### -field pfnCreateDescriptorHeap

Points to a function that creates a descriptor heap.

### -field pfnDestroyDescriptorHeap

Points to a function that destroys a descriptor heap.

### -field pfnGetDescriptorSizeInBytes

Points to a function that gets a descriptor's size in bytes.

### -field pfnGetCPUDescriptorHandleForHeapStart

Points to a function that gets a CPU descriptor handle for heap start.

### -field pfnGetGPUDescriptorHandleForHeapStart

Points to a function that gets a GPU descriptor handle for heap start.

### -field pfnCreateShaderResourceView

Points to a function that creates a shader resource view.

### -field pfnCreateConstantBufferView

Points to a function that creates a constant buffer view.

### -field pfnCreateSampler

Points to a function that creates a sampler.

### -field pfnCreateUnorderedAccessView

Points to a function that creates an unordered access view.

### -field pfnCreateRenderTargetView

Points to a function that creates a render target view.

### -field pfnCreateDepthStencilView

Points to a function that creates a depth stencil view.

### -field pfnCalcPrivateRootSignatureSize

Points to a function that calculates a private root signature size.

### -field pfnCreateRootSignature

Points to a function that creates a root signature.

### -field pfnDestroyRootSignature

Points to a function that destroys a root signature.

### -field pfnMapHeap

Points to a function that maps a heap into the application's address space.

### -field pfnUnmapHeap

Points to a function that unmaps a previously mapped heap from the application's address space.

### -field pfnCalcPrivateHeapAndResourceSizes

Points to a function that calculates the size of the private heap and resource.

### -field pfnCreateHeapAndResource

Points to a function that creates a heap and associated resource.

### -field pfnDestroyHeapAndResource

Points to a function that destroys a heap and its associated resource.

### -field pfnMakeResident

Points to a function that makes a set of resources resident in physical memory.

### -field pfnEvict

Points to a function that evicts a set of resources from physical memory.

### -field pfnCalcPrivateOpenedHeapAndResourceSizes

Points to a function that calculates the size of the private heap and resource for opened resources.

### -field pfnOpenHeapAndResource

Points to a function that opens a heap and resource created by another process.

### -field pfnCopyDescriptors

Points to a function that copies an array of descriptors to the destination descriptor heap.

### -field pfnCopyDescriptorsSimple

Points to a function that copies descriptors to the destination descriptor heap using a simple method.

### -field pfnCalcPrivateQueryHeapSize

Points to a function that calculates the size of the private query heap.

### -field pfnCreateQueryHeap

Points to a function that creates a query heap.

### -field pfnDestroyQueryHeap

Points to a function that destroys a query heap.

### -field pfnCalcPrivateCommandSignatureSize

Points to a function that calculates the size of the private command signature.

### -field pfnCreateCommandSignature

Points to a function that creates a command signature.

### -field pfnDestroyCommandSignature

Points to a function that destroys a command signature.

### -field pfnCheckResourceVirtualAddress

Points to a function that checks if a resource's virtual address is valid.

### -field pfnCheckResourceAllocationInfo

Points to a function that checks the allocation information for a given resource.

### -field pfnCheckSubresourceInfo

Points to a function that checks the information of a subresource within a resource.

### -field pfnCheckExistingResourceAllocationInfo

Points to a function that checks the allocation information for an existing resource.

### -field pfnOfferResources

Points to a function that offers resources to the operating system, allowing them to be paged out.

### -field pfnReclaimResources

Points to a function that reclaims resources that were previously offered to the operating system.

### -field pfnGetImplicitPhysicalAdapterMask

Points to a function that gets the mask of physical adapters that can be used implicitly by a device.

### -field pfnGetPresentPrivateDriverDataSize

Points to a function that gets the size of private driver data for present operations.

### -field pfnQueryNodeMap

Points to a function that queries the mapping of nodes within a multi-adapter configuration.

### -field pfnRetrieveShaderComment

Points to a function that retrieves the comment string embedded in a shader.

### -field pfnCheckResourceAllocationHandle

Points to a function that checks the allocation handle for a resource.

### -field pfnCalcPrivatePipelineLibrarySize

Points to a function that calculates the size of the private pipeline library.

### -field pfnCreatePipelineLibrary

Points to a function that creates a pipeline library.

### -field pfnDestroyPipelineLibrary

Points to a function that destroys a pipeline library.

### -field pfnAddPipelineStateToLibrary

Points to a function that adds a pipeline state object to a pipeline library.

### -field pfnCalcSerializedLibrarySize

Points to a function that calculates the size of a serialized pipeline library.

### -field pfnSerializeLibrary

Points to a function that serializes a library.

### -field pfnGetDebugAllocationInfo

Points to a function that gets debug allocation info.

### -field pfnCalcPrivateCommandRecorderSize

Points to a function that calculates private command recorder size.

### -field pfnCreateCommandRecorder

Points to a function that creates a command recorder.

### -field pfnDestroyCommandRecorder

Points to a function that destroys a command recorder.

### -field pfnCommandRecorderSetCommandPoolAsTarget

Points to a function that sets the command pool as target for the command recorder.

### -field pfnCalcPrivateSchedulingGroupSize

Points to a function that calculates private scheduling group size.

### -field pfnCreateSchedulingGroup

Points to a function that creates a scheduling group.

### -field pfnDestroySchedulingGroup

Points to a function that destroys a scheduling group.

### -field pfnEnumerateMetaCommands

Points to a function that enumerates meta-commands.

### -field pfnEnumerateMetaCommandParameters

Points to a function that enumerates meta-command parameters.

### -field pfnCalcPrivateMetaCommandSize

Points to a function that calculates private meta-command size.

### -field pfnCreateMetaCommand

Points to a function that creates a meta-command.

### -field pfnDestroyMetaCommand

Points to a function that destroys a meta-command.

### -field pfnGetMetaCommandRequiredParameterInfo

Points to a function that gets required meta-command parameter info.

### -field pfnCalcPrivateStateObjectSize

Points to a function that calculates private state object size.

### -field pfnCreateStateObject

Points to a function that creates a state object.

### -field pfnDestroyStateObject

Points to a function that destroys a state object.

### -field pfnGetRaytracingAccelerationStructurePrebuildInfo

Points to a function that gets ray tracing acceleration structure prebuild info.

### -field pfnCheckDriverMatchingIdentifier

Points to a function that checks driver matching identifier.

### -field pfnGetShaderIdentifier

Points to a function that gets a shader identifier.

### -field pfnGetShaderStackSize

Points to a function that gets a shader stack size.

### -field pfnGetPipelineStackSize

Points to a function that gets a pipeline stack size.

### -field pfnSetPipelineStackSize

Points to a function that sets pipeline stack size.

### -field pfnSetBackgroundProcessingMode

Points to a function that sets the background processing mode.

### -field pfnCalcPrivateAddToStateObjectSize

Points to a function that calculates private add to state object size. See the [DirectX Raytracing (DXR) Functional Spec](https://microsoft.github.io/DirectX-Specs/d3d/Raytracing.html) for more information.

### -field pfnAddToStateObject

Points to a function that adds to state object. See the [DirectX Raytracing (DXR) Functional Spec](https://microsoft.github.io/DirectX-Specs/d3d/Raytracing.html) for more information.

### -field pfnCreateSamplerFeedbackUnorderedAccessView

Points to a function that creates a sampler feedback unordered access view. See the [D3D Sampler Feedback Specification](https://microsoft.github.io/DirectX-Specs/d3d/SamplerFeedback.html) for more information.

### -field pfnCreateAmplificationShader

Points to a function that creates an amplification shader. See the [Mesh Shader Specification](https://microsoft.github.io/DirectX-Specs/d3d/MeshShader.html) for more information.

### -field pfnCreateMeshShader

Points to a function that creates a mesh shader. See the [Mesh Shader Specification](https://microsoft.github.io/DirectX-Specs/d3d/MeshShader.html) for more information.

### -field pfnCalcPrivateMeshShaderSize

Points to a function that calculates private mesh shader size. See the [Mesh Shader Specification](https://microsoft.github.io/DirectX-Specs/d3d/MeshShader.html) for more information.

### -field pfnImplicitShaderCacheControl

Pointer to a function for implicit shader cache control. See the [D3D12 Shader Cache APIs specification](https://microsoft.github.io/DirectX-Specs/d3d/ShaderCache.html) for more information.

### -field pfnGetProgramIdentifier

Points to a function that identifies a program for the purpose of setting it on a command list. See the [D3D12 Work Graphs specification](https://github.com/microsoft/DirectX-Specs/blob/master/d3d/WorkGraphs.md) for more information.

### -field pfnGetWorkGraphMemoryRequirements

Points to a function that gets the work graph memory requirements. See the [D3D12 Work Graphs specification](https://github.com/microsoft/DirectX-Specs/blob/master/d3d/WorkGraphs.md) for more information.

## -see-also

[**D3D12DDI_TABLE_TYPE**](ne-d3d12umddi-d3d12ddi_table_type.md)

[**PFND3D12DDI_FILLDDITTABLE**](nc-d3d12umddi-pfnd3d12ddi_fillddittable.md)
