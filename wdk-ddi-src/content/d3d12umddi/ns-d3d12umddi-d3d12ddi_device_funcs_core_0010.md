---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_CORE_0010
title: D3D12DDI_DEVICE_FUNCS_CORE_0010 (d3d12umddi.h)
description: Contains core functions.
old-location: display\d3d12ddi_device_funcs_core_0010.htm
ms.assetid: 87B4873E-DD44-47E9-8E6A-5BA91218188F
ms.date: 04/16/2018
keywords: ["D3D12DDI_DEVICE_FUNCS_CORE_0010 structure"]
ms.keywords: D3D12DDI_DEVICE_FUNCS_CORE_0010, D3D12DDI_DEVICE_FUNCS_CORE_0010 structure [Display Devices], d3d12umddi/D3D12DDI_DEVICE_FUNCS_CORE_0010, display.d3d12ddi_device_funcs_core_0010
f1_keywords:
 - "d3d12umddi/D3D12DDI_DEVICE_FUNCS_CORE_0010"
 - "D3D12DDI_DEVICE_FUNCS_CORE_0010"
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
req.lib:
req.dll:
req.irql:
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d12umddi.h
api_name:
- D3D12DDI_DEVICE_FUNCS_CORE_0010
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_DEVICE_FUNCS_CORE_0010
---

# D3D12DDI_DEVICE_FUNCS_CORE_0010 structure


## -description


Contains core functions.


## -struct-fields




### -field pfnCheckFormatSupport

A function that checks format support. See [pfnCheckFormatSupport](nc-d3d12umddi-pfnd3d12ddi_checkformatsupport.md).


### -field pfnCheckMultisampleQualityLevels

A function that checks multi-sample quality levels. See [pfnCheckMultisampleQualityLevels](nc-d3d12umddi-pfnd3d12ddi_checkmultisamplequalitylevels.md).


### -field pfnGetMipPacking

A function that gets MIP packing. See [pfnGetMipPacking](nc-d3d12umddi-pfnd3d12ddi_getmippacking.md).


### -field pfnCalcPrivateElementLayoutSize

A function that calculates layout size for a private element. [pfnCalcPrivateElementLayoutSize](nc-d3d12umddi-pfnd3d12ddi_calcprivateelementlayoutsize_0010.md).


### -field pfnCreateElementLayout

A function that creates an element layout. See [pfnCreateElementLayout](nc-d3d12umddi-pfnd3d12ddi_createelementlayout_0010.md).


### -field pfnDestroyElementLayout

A function that destroys an element layout. See [pfnDestroyElementLayout](nc-d3d12umddi-pfnd3d12ddi_destroyelementlayout.md).


### -field pfnCalcPrivateBlendStateSize

A function that calculates the size of a private blend state. See [pfnCalcPrivateBlendStateSize](nc-d3d12umddi-pfnd3d12ddi_calcprivateblendstatesize_0010.md).


### -field pfnCreateBlendState

A function that creates a blend state. See [pfnCreateBlendState](nc-d3d12umddi-pfnd3d12ddi_createblendstate_0010.md).


### -field pfnDestroyBlendState

A function that destroys a blend state. See [pfnDestroyBlendState](nc-d3d12umddi-pfnd3d12ddi_destroyblendstate.md).


### -field pfnCalcPrivateDepthStencilStateSize

A function that calculates the size of the state of a private depth stencil. See [pfnCalcPrivateDepthStencilStateSize](nc-d3d12umddi-pfnd3d12ddi_calcprivatedepthstencilstatesize_0010.md).


### -field pfnCreateDepthStencilState

A function that creates a depth stencil state. See [pfnCreateDepthStencilState](nc-d3d12umddi-pfnd3d12ddi_createdepthstencilstate_0010.md).


### -field pfnDestroyDepthStencilState

A function that destroys a depth stencil state. See [pfnDestroyDepthStencilState](nc-d3d12umddi-pfnd3d12ddi_destroydepthstencilstate.md).


### -field pfnCalcPrivateRasterizerStateSize

A function that calculates the size of a private rasterizer state. See [pfnCalcPrivateRasterizerStateSize](nc-d3d12umddi-pfnd3d12ddi_calcprivaterasterizerstatesize_0010.md).


### -field pfnCreateRasterizerState

A function that creates a rasterizer state. See [pfnCreateRasterizerState](nc-d3d12umddi-pfnd3d12ddi_createrasterizerstate_0010.md).


### -field pfnDestroyRasterizerState

A function that destroys a rasterizer state. See [pfnDestroyRasterizerState](nc-d3d12umddi-pfnd3d12ddi_destroyrasterizerstate.md).


### -field pfnCalcPrivateShaderSize

A function that calculates the size of a private shader. See [pfnCalcPrivateShaderSize](nc-d3d12umddi-pfnd3d12ddi_calc_private_shader_size_0010.md).


### -field pfnCreateVertexShader

A function that creates a vertex shader. See [PFND3D12DDI_CREATE_SHADER_0010](nc-d3d12umddi-pfnd3d12ddi_create_shader_0010.md).


### -field pfnCreatePixelShader

A function that creates a shader. See [PFND3D12DDI_CREATE_SHADER_0010](nc-d3d12umddi-pfnd3d12ddi_create_shader_0010.md).


### -field pfnCreateGeometryShader

A function that creates a geometry shader. See [PFND3D12DDI_CREATE_SHADER_0010](nc-d3d12umddi-pfnd3d12ddi_create_shader_0010.md).


### -field pfnCreateComputeShader

A function that creates a compute shader. See [PFND3D12DDI_CREATE_SHADER_0010](nc-d3d12umddi-pfnd3d12ddi_create_shader_0010.md).


### -field pfnCalcPrivateGeometryShaderWithStreamOutput

A function that calculates a private geometry shader with stream output. See [pfnCalcPrivateGeometryShaderWithStreamOutput](nc-d3d12umddi-pfnd3d12ddi_calc_private_geometry_shader_with_stream_output_0010.md).


### -field pfnCreateGeometryShaderWithStreamOutput

A function that creates a private geometry shader with stream output. See [pfnCreateGeometryShaderWithStreamOutput](nc-d3d12umddi-pfnd3d12ddi_create_geometry_shader_with_stream_output_0010.md).


### -field pfnCalcPrivateTessellationShaderSize

A function that creates private tessellation shader size. See [pfnCalcPrivateTessellationShaderSize](nc-d3d12umddi-pfnd3d12ddi_calc_private_shader_size_0010.md).


### -field pfnCreateHullShader

A function that creates a hull shader. See [pfnCreateHullShader](nc-d3d12umddi-pfnd3d12ddi_create_shader_0010.md).


### -field pfnCreateDomainShader

A function that creates a domain shader. See [pfnCreateDomainShader](nc-d3d12umddi-pfnd3d12ddi_create_shader_0010.md).


### -field pfnDestroyShader

A function that destroys a shader. See [pfnDestroyShader](nc-d3d12umddi-pfnd3d12ddi_destroyshader.md).


### -field pfnCalcPrivateCommandQueueSize

A function that calculates the size of a private queue. See [pfnCalcPrivateCommandQueueSize](nc-d3d12umddi-pfnd3d12ddi_calcprivatecommandqueuesize_0001.md).


### -field pfnCreateCommandQueue

A function that creates a command queue. See [pfnCreateCommandQueue](nc-d3d12umddi-pfnd3d12ddi_createcommandqueue_0001.md).


### -field pfnDestroyCommandQueue

A function that destroys a command queue. See [pfnDestroyCommandQueue](nc-d3d12umddi-pfnd3d12ddi_destroycommandqueue.md).


### -field pfnCalcPrivateCommandAllocatorSize

A function that calculates the size of a private command allocator. See [pfnCalcPrivateCommandAllocatorSize](nc-d3d12umddi-pfnd3d12ddi_calcprivatecommandallocatorsize.md).


### -field pfnCreateCommandAllocator

A function that creates a command allocator. See [pfnCreateCommandAllocator](nc-d3d12umddi-pfnd3d12ddi_createcommandallocator.md).


### -field pfnDestroyCommandAllocator

A function that destroys a command allocator. See [pfnDestroyCommandAllocator](nc-d3d12umddi-pfnd3d12ddi_destroycommandallocator.md).


### -field pfnResetCommandAllocator

A function that resets a command allocator. See [pfnResetCommandAllocator](nc-d3d12umddi-pfnd3d12ddi_resetcommandallocator.md).


### -field pfnCalcPrivatePipelineStateSize

A function that calculate the size of a private pipeline state. See [pfnCalcPrivatePipelineStateSize](nc-d3d12umddi-pfnd3d12ddi_calc_private_pipeline_state_size_0010.md).


### -field pfnCreatePipelineState

A function that crates a pipeline state. See [pfnCreatePipelineState](nc-d3d12umddi-pfnd3d12ddi_create_pipeline_state_0010.md).


### -field pfnDestroyPipelineState

A function that destroys a pipeline state. See [pfnDestroyPipelineState](nc-d3d12umddi-pfnd3d12ddi_destroy_pipeline_state.md).


### -field pfnCalcPrivateCommandListSize

A function that calculate the size of a private command list. See [pfnCalcPrivateCommandListSize](nc-d3d12umddi-pfnd3d12ddi_calc_private_command_list_size_0001.md).


### -field pfnCreateCommandList

A function that creates a command list. See [pfnCreateCommandList](nc-d3d12umddi-pfnd3d12ddi_create_command_list_0001.md).


### -field pfnDestroyCommandList

A function that destroys a command list. See [pfnDestroyCommandList](nc-d3d12umddi-pfnd3d12ddi_destroycommandlist.md).


### -field pfnCalcPrivateFenceSize

A function that calculates a private fence size. See [pfnCalcPrivateFenceSize](nc-d3d12umddi-pfnd3d12ddi_calcprivatefencesize.md).


### -field pfnCreateFence

A function that creates a fence. See [pfnCreateFence](nc-d3d12umddi-pfnd3d12ddi_createfence.md).


### -field pfnDestroyFence

A function that destroys a fence. See [pfnDestroyFence](nc-d3d12umddi-pfnd3d12ddi_destroyfence.md).


### -field pfnCalcPrivateDescriptorHeapSize

A function that calculates the size of a private descriptor heap. See [pfnCalcPrivateDescriptorHeapSize](nc-d3d12umddi-pfnd3d12ddi_calc_private_descriptor_heap_size_0001.md).


### -field pfnCreateDescriptorHeap

A function that creates a descriptor heap. See [pfnCreateDescriptorHeap](nc-d3d12umddi-pfnd3d12ddi_create_descriptor_heap_0001.md).


### -field pfnDestroyDescriptorHeap

A function that destroys a descriptor heap. See [pfnDestroyDescriptorHeap](nc-d3d12umddi-pfnd3d12ddi_destroy_descriptor_heap.md).


### -field pfnGetDescriptorSizeInBytes

A function that gets the descriptor size, in bytes. See [pfnGetDescriptorSizeInBytes](nc-d3d12umddi-pfnd3d12ddi_get_descriptor_size_in_bytes.md).


### -field pfnGetCPUDescriptorHandleForHeapStart

A function that gets a CPU descriptor handle. See [pfnGetCPUDescriptorHandleForHeapStart](nc-d3d12umddi-pfnd3d12ddi_get_cpu_descriptor_handle_for_heap_start.md).


### -field pfnGetGPUDescriptorHandleForHeapStart

A function that gets a GPU descriptor handle. See [pfnGetGPUDescriptorHandleForHeapStart](nc-d3d12umddi-pfnd3d12ddi_get_gpu_descriptor_handle_for_heap_start.md).


### -field pfnCreateShaderResourceView

A function that creates a shader resource view. See [pfnCreateShaderResourceView](nc-d3d12umddi-pfnd3d12ddi_create_shader_resource_view_0002.md).


### -field pfnCreateConstantBufferView

A function that creates a constant buffer view. See [pfnCreateConstantBufferView](nc-d3d12umddi-pfnd3d12ddi_create_constant_buffer_view.md).


### -field pfnCreateSampler

A function that creates a sampler. See [pfnCreateSampler](nc-d3d12umddi-pfnd3d12ddi_create_sampler.md).


### -field pfnCreateUnorderedAccessView

A function that creates an unordered access view. See [pfnCreateUnorderedAccessView](nc-d3d12umddi-pfnd3d12ddi_create_unordered_access_view_0002.md).


### -field pfnCreateRenderTargetView

A function that creates a render target view. See [pfnCreateRenderTargetView](nc-d3d12umddi-pfnd3d12ddi_create_render_target_view_0002.md).


### -field pfnCreateDepthStencilView

A function that creates a depth stencil view. See [pfnCreateDepthStencilView](nc-d3d12umddi-pfnd3d12ddi_create_depth_stencil_view.md).


### -field pfnCalcPrivateRootSignatureSize

A function that calculates the size of a private root signature. See [pfnCalcPrivateRootSignatureSize](nc-d3d12umddi-pfnd3d12ddi_calc_private_root_signature_size_0001.md).


### -field pfnCreateRootSignature

A function that creates a root signature. See [pfnCreateRootSignature](nc-d3d12umddi-pfnd3d12ddi_create_root_signature_0001.md).


### -field pfnDestroyRootSignature

A function that destroys a root signature. See [pfnDestroyRootSignature](nc-d3d12umddi-pfnd3d12ddi_destroy_root_signature.md).


### -field pfnMapHeap

A function that maps a heap. See [pfnMapHeap](nc-d3d12umddi-pfnd3d12ddi_mapheap.md).


### -field pfnUnmapHeap

A function that unmaps a heap. See [pfnUnmapHeap](nc-d3d12umddi-pfnd3d12ddi_unmapheap.md).


### -field pfnCalcPrivateHeapAndResourceSizes

A function that calculates sizes for private heap and resource. See [pfnCalcPrivateHeapAndResourceSizes](nc-d3d12umddi-pfnd3d12ddi_calcprivateheapandresourcesizes_0003.md).


### -field pfnCreateHeapAndResource

A function that create a heap and resource. See [pfnCreateHeapAndResource](nc-d3d12umddi-pfnd3d12ddi_createheapandresource_0003.md).


### -field pfnDestroyHeapAndResource

A function that destroys a heap and resource. See [pfnDestroyHeapAndResource](nc-d3d12umddi-pfnd3d12ddi_destroyheapandresource.md).


### -field pfnMakeResident

A function that makes a resident. See [pfnMakeResident](nc-d3d12umddi-pfnd3d12ddi_makeresident_0001.md).


### -field pfnEvict

A function that evicts. See [pfnEvict](nc-d3d12umddi-pfnd3d12ddi_evict2.md).


### -field pfnCalcPrivateOpenedHeapAndResourceSizes

A function that calculates sizes for private opened heap and resources. See [pfnCalcPrivateOpenedHeapAndResourceSizes](nc-d3d12umddi-pfnd3d12ddi_calcprivateopenedheapandresourcesizes_0003.md).


### -field pfnOpenHeapAndResource

A function that opens a heap and resource. See [pfnOpenHeapAndResource](nc-d3d12umddi-pfnd3d12ddi_openheapandresource_0003.md).


### -field pfnCopyDescriptors

A function that copies descriptors. See [pfnCopyDescriptors](nc-d3d12umddi-pfnd3d12ddi_copy_descriptors_0003.md).


### -field pfnCopyDescriptorsSimple

A function that does a simple copy of descriptors. See [pfnCopyDescriptorsSimple](nc-d3d12umddi-pfnd3d12ddi_copy_descriptors_simple_0003.md).


### -field pfnCalcPrivateQueryHeapSize

A function that calculates the size of a private query heap. See [pfnCalcPrivateQueryHeapSize](nc-d3d12umddi-pfnd3d12ddi_calc_private_query_heap_size_0001.md).


### -field pfnCreateQueryHeap

A function that creates a query heap. See [pfnCreateQueryHeap](nc-d3d12umddi-pfnd3d12ddi_create_query_heap_0001.md).


### -field pfnDestroyQueryHeap

A function that destroys a query heap. See [pfnDestroyQueryHeap](nc-d3d12umddi-pfnd3d12ddi_destroy_query_heap.md).


### -field pfnCalcPrivateCommandSignatureSize

A function that calculates the size of a private command signature. See [pfnCalcPrivateCommandSignatureSize](nc-d3d12umddi-pfnd3d12ddi_calc_private_command_signature_size_0001.md).


### -field pfnCreateCommandSignature

A function that creates a command signature. See [pfnCreateCommandSignature](nc-d3d12umddi-pfnd3d12ddi_create_command_signature_0001.md).


### -field pfnDestroyCommandSignature

A function that destroys a command signature. See [pfnDestroyCommandSignature](nc-d3d12umddi-pfnd3d12ddi_destroy_command_signature.md).


### -field pfnCheckResourceVirtualAddress

A function that checks the virtual address of a resource. See [pfnCheckResourceVirtualAddress](nc-d3d12umddi-pfnd3d12ddi_checkresourcevirtualaddress.md).


### -field pfnCheckResourceAllocationInfo

A function that checks allocation information of a resource. See [pfnCheckResourceAllocationInfo](nc-d3d12umddi-pfnd3d12ddi_checkresourceallocationinfo_0003.md).


### -field pfnCheckSubresourceInfo

A function that checks information of a subresource. See [pfnCheckSubresourceInfo](nc-d3d12umddi-pfnd3d12ddi_checksubresourceinfo.md).


### -field pfnCheckExistingResourceAllocationInfo

A function that checks allocation information of an existing resource. See [pfnCheckExistingResourceAllocationInfo](nc-d3d12umddi-pfnd3d12ddi_checkexisitingresourceallocationinfo.md).


### -field pfnOfferResources

A function that offers resources. See [pfnOfferResources](nc-d3d12umddi-pfnd3d12ddi_offerresources.md).


### -field pfnReclaimResources

A function that reclaims resources. See [pfnReclaimResources](nc-d3d12umddi-pfnd3d12ddi_reclaimresources_0001.md).


### -field pfnGetImplicitPhysicalAdapterMask

A function that gets an implicit physical adapter mask. See [pfnGetImplicitPhysicalAdapterMask](nc-d3d12umddi-pfnd3d12ddi_getimplicitphysicaladaptermask.md).


### -field pfnGetPresentPrivateDriverDataSize

A function that gets the present size of private driver data. See [pfnGetPresentPrivateDriverDataSize](nc-d3d12umddi-pfnd3d12ddi_get_present_private_driver_data_size.md).


### -field pfnQueryNodeMap

A function that queries a node map. See [pfnQueryNodeMap](nc-d3d12umddi-pfnd3d12ddi_query_node_map.md).


### -field pfnRetrieveShaderComment

A function that retrieves a shader comment. See [pfnRetrieveShaderComment](nc-d3d12umddi-pfnd3d12ddi_retrieve_shader_comment_0003.md).


### -field pfnCheckResourceAllocationHandle

A function that checks a resource allocation handle. See [pfnCheckResourceAllocationHandle](nc-d3d12umddi-pfnd3d12ddi_checkresourceallocationhandle.md).


### -field pfnCalcPrivatePipelineLibrarySize

A function that calculates the size of a private pipeline library. See [pfnCalcPrivatePipelineLibrarySize](nc-d3d12umddi-pfnd3d12ddi_calc_private_pipeline_library_size_0010.md).


### -field pfnCreatePipelineLibrary

A function that creates a pipeline library. See [pfnCreatePipelineLibrary](nc-d3d12umddi-pfnd3d12ddi_create_pipeline_library_0010.md).


### -field pfnDestroyPipelineLibrary

A function that destroys a pipeline library. See [pfnDestroyPipelineLibrary](nc-d3d12umddi-pfnd3d12ddi_destroy_pipeline_library_0010.md).


### -field pfnAddPipelineStateToLibrary

A function that adds pipeline state to a library. See [pfnAddPipelineStateToLibrary](nc-d3d12umddi-pfnd3d12ddi_add_pipeline_state_to_library_0010.md).


### -field pfnCalcSerializedLibrarySize

A function that calculates the size of a serialized library. See [pfnCalcSerializedLibrarySize](nc-d3d12umddi-pfnd3d12ddi_calc_serialized_library_size_0010.md).


### -field pfnSerializeLibrary

A function that serializes a library. See [pfnSerializeLibrary](nc-d3d12umddi-pfnd3d12ddi_serialize_library_0010.md).



 

 

