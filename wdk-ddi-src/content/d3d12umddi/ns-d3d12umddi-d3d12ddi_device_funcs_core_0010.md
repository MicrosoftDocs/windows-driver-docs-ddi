---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_CORE_0010
title: D3D12DDI_DEVICE_FUNCS_CORE_0010
author: windows-driver-content
description: Contains core functions.
old-location: display\d3d12ddi_device_funcs_core_0010.htm
old-project: display
ms.assetid: 87B4873E-DD44-47E9-8E6A-5BA91218188F
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3d12ddi_device_funcs_core_0010, D3D12DDI_DEVICE_FUNCS_CORE_0010, d3d12umddi/D3D12DDI_DEVICE_FUNCS_CORE_0010, D3D12DDI_DEVICE_FUNCS_CORE_0010 structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d12umddi.h
apiname:
-	D3D12DDI_DEVICE_FUNCS_CORE_0010
product: Windows
targetos: Windows
req.typenames: D3D12DDI_DEVICE_FUNCS_CORE_0010
---

# D3D12DDI_DEVICE_FUNCS_CORE_0010 structure


## -description


Contains core functions.


## -syntax


````
typedef struct D3D12DDI_DEVICE_FUNCS_CORE_0010 {
  PFND3D12DDI_CHECKFORMATSUPPORT                                   pfnCheckFormatSupport;
  PFND3D12DDI_CHECKMULTISAMPLEQUALITYLEVELS                        pfnCheckMultisampleQualityLevels;
  PFND3D12DDI_GETMIPPACKING                                        pfnGetMipPacking;
  PFND3D12DDI_CALCPRIVATEELEMENTLAYOUTSIZE_0010                    pfnCalcPrivateElementLayoutSize;
  PFND3D12DDI_CREATEELEMENTLAYOUT_0010                             pfnCreateElementLayout;
  PFND3D12DDI_DESTROYELEMENTLAYOUT                                 pfnDestroyElementLayout;
  PFND3D12DDI_CALCPRIVATEBLENDSTATESIZE_0010                       pfnCalcPrivateBlendStateSize;
  PFND3D12DDI_CREATEBLENDSTATE_0010                                pfnCreateBlendState;
  PFND3D12DDI_DESTROYBLENDSTATE                                    pfnDestroyBlendState;
  PFND3D12DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE_0010                pfnCalcPrivateDepthStencilStateSize;
  PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0010                         pfnCreateDepthStencilState;
  PFND3D12DDI_DESTROYDEPTHSTENCILSTATE                             pfnDestroyDepthStencilState;
  PFND3D12DDI_CALCPRIVATERASTERIZERSTATESIZE_0010                  pfnCalcPrivateRasterizerStateSize;
  PFND3D12DDI_CREATERASTERIZERSTATE_0010                           pfnCreateRasterizerState;
  PFND3D12DDI_DESTROYRASTERIZERSTATE                               pfnDestroyRasterizerState;
  PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE_0010                        pfnCalcPrivateShaderSize;
  PFND3D12DDI_CREATE_SHADER_0010                                   pfnCreateVertexShader;
  PFND3D12DDI_CREATE_SHADER_0010                                   pfnCreatePixelShader;
  PFND3D12DDI_CREATE_SHADER_0010                                   pfnCreateGeometryShader;
  PFND3D12DDI_CREATE_SHADER_0010                                   pfnCreateComputeShader;
  PFND3D12DDI_CALC_PRIVATE_GEOMETRY_SHADER_WITH_STREAM_OUTPUT_0010 pfnCalcPrivateGeometryShaderWithStreamOutput;
  PFND3D12DDI_CREATE_GEOMETRY_SHADER_WITH_STREAM_OUTPUT_0010       pfnCreateGeometryShaderWithStreamOutput;
  PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE_0010                        pfnCalcPrivateTessellationShaderSize;
  PFND3D12DDI_CREATE_SHADER_0010                                   pfnCreateHullShader;
  PFND3D12DDI_CREATE_SHADER_0010                                   pfnCreateDomainShader;
  PFND3D12DDI_DESTROYSHADER                                        pfnDestroyShader;
  PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0001                     pfnCalcPrivateCommandQueueSize;
  PFND3D12DDI_CREATECOMMANDQUEUE_0001                              pfnCreateCommandQueue;
  PFND3D12DDI_DESTROYCOMMANDQUEUE                                  pfnDestroyCommandQueue;
  PFND3D12DDI_CALCPRIVATECOMMANDALLOCATORSIZE                      pfnCalcPrivateCommandAllocatorSize;
  PFND3D12DDI_CREATECOMMANDALLOCATOR                               pfnCreateCommandAllocator;
  PFND3D12DDI_DESTROYCOMMANDALLOCATOR                              pfnDestroyCommandAllocator;
  PFND3D12DDI_RESETCOMMANDALLOCATOR                                pfnResetCommandAllocator;
  PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0010                pfnCalcPrivatePipelineStateSize;
  PFND3D12DDI_CREATE_PIPELINE_STATE_0010                           pfnCreatePipelineState;
  PFND3D12DDI_DESTROY_PIPELINE_STATE                               pfnDestroyPipelineState;
  PFND3D12DDI_CALC_PRIVATE_COMMAND_LIST_SIZE_0001                  pfnCalcPrivateCommandListSize;
  PFND3D12DDI_CREATE_COMMAND_LIST_0001                             pfnCreateCommandList;
  PFND3D12DDI_DESTROYCOMMANDLIST                                   pfnDestroyCommandList;
  PFND3D12DDI_CALCPRIVATEFENCESIZE                                 pfnCalcPrivateFenceSize;
  PFND3D12DDI_CREATEFENCE                                          pfnCreateFence;
  PFND3D12DDI_DESTROYFENCE                                         pfnDestroyFence;
  PFND3D12DDI_CALC_PRIVATE_DESCRIPTOR_HEAP_SIZE_0001               pfnCalcPrivateDescriptorHeapSize;
  PFND3D12DDI_CREATE_DESCRIPTOR_HEAP_0001                          pfnCreateDescriptorHeap;
  PFND3D12DDI_DESTROY_DESCRIPTOR_HEAP                              pfnDestroyDescriptorHeap;
  PFND3D12DDI_GET_DESCRIPTOR_SIZE_IN_BYTES                         pfnGetDescriptorSizeInBytes;
  PFND3D12DDI_GET_CPU_DESCRIPTOR_HANDLE_FOR_HEAP_START             pfnGetCPUDescriptorHandleForHeapStart;
  PFND3D12DDI_GET_GPU_DESCRIPTOR_HANDLE_FOR_HEAP_START             pfnGetGPUDescriptorHandleForHeapStart;
  PFND3D12DDI_CREATE_SHADER_RESOURCE_VIEW_0002                     pfnCreateShaderResourceView;
  PFND3D12DDI_CREATE_CONSTANT_BUFFER_VIEW                          pfnCreateConstantBufferView;
  PFND3D12DDI_CREATE_SAMPLER                                       pfnCreateSampler;
  PFND3D12DDI_CREATE_UNORDERED_ACCESS_VIEW_0002                    pfnCreateUnorderedAccessView;
  PFND3D12DDI_CREATE_RENDER_TARGET_VIEW_0002                       pfnCreateRenderTargetView;
  PFND3D12DDI_CREATE_DEPTH_STENCIL_VIEW                            pfnCreateDepthStencilView;
  PFND3D12DDI_CALC_PRIVATE_ROOT_SIGNATURE_SIZE_0001                pfnCalcPrivateRootSignatureSize;
  PFND3D12DDI_CREATE_ROOT_SIGNATURE_0001                           pfnCreateRootSignature;
  PFND3D12DDI_DESTROY_ROOT_SIGNATURE                               pfnDestroyRootSignature;
  PFND3D12DDI_MAPHEAP                                              pfnMapHeap;
  PFND3D12DDI_UNMAPHEAP                                            pfnUnmapHeap;
  PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0003                 pfnCalcPrivateHeapAndResourceSizes;
  PFND3D12DDI_CREATEHEAPANDRESOURCE_0003                           pfnCreateHeapAndResource;
  PFND3D12DDI_DESTROYHEAPANDRESOURCE                               pfnDestroyHeapAndResource;
  PFND3D12DDI_MAKERESIDENT_0001                                    pfnMakeResident;
  PFND3D12DDI_EVICT2                                               pfnEvict;
  PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0003           pfnCalcPrivateOpenedHeapAndResourceSizes;
  PFND3D12DDI_OPENHEAPANDRESOURCE_0003                             pfnOpenHeapAndResource;
  PFND3D12DDI_COPY_DESCRIPTORS_0003                                pfnCopyDescriptors;
  PFND3D12DDI_COPY_DESCRIPTORS_SIMPLE_0003                         pfnCopyDescriptorsSimple;
  PFND3D12DDI_CALC_PRIVATE_QUERY_HEAP_SIZE_0001                    pfnCalcPrivateQueryHeapSize;
  PFND3D12DDI_CREATE_QUERY_HEAP_0001                               pfnCreateQueryHeap;
  PFND3D12DDI_DESTROY_QUERY_HEAP                                   pfnDestroyQueryHeap;
  PFND3D12DDI_CALC_PRIVATE_COMMAND_SIGNATURE_SIZE_0001             pfnCalcPrivateCommandSignatureSize;
  PFND3D12DDI_CREATE_COMMAND_SIGNATURE_0001                        pfnCreateCommandSignature;
  PFND3D12DDI_DESTROY_COMMAND_SIGNATURE                            pfnDestroyCommandSignature;
  PFND3D12DDI_CHECKRESOURCEVIRTUALADDRESS                          pfnCheckResourceVirtualAddress;
  PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0003                     pfnCheckResourceAllocationInfo;
  PFND3D12DDI_CHECKSUBRESOURCEINFO                                 pfnCheckSubresourceInfo;
  PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO                 pfnCheckExistingResourceAllocationInfo;
  PFND3D12DDI_OFFERRESOURCES                                       pfnOfferResources;
  PFND3D12DDI_RECLAIMRESOURCES_0001                                pfnReclaimResources;
  PFND3D12DDI_GETIMPLICITPHYSICALADAPTERMASK                       pfnGetImplicitPhysicalAdapterMask;
  PFND3D12DDI_GET_PRESENT_PRIVATE_DRIVER_DATA_SIZE                 pfnGetPresentPrivateDriverDataSize;
  PFND3D12DDI_QUERY_NODE_MAP                                       pfnQueryNodeMap;
  PFND3D12DDI_RETRIEVE_SHADER_COMMENT_0003                         pfnRetrieveShaderComment;
  PFND3D12DDI_CHECKRESOURCEALLOCATIONHANDLE                        pfnCheckResourceAllocationHandle;
  PFND3D12DDI_CALC_PRIVATE_PIPELINE_LIBRARY_SIZE_0010              pfnCalcPrivatePipelineLibrarySize;
  PFND3D12DDI_CREATE_PIPELINE_LIBRARY_0010                         pfnCreatePipelineLibrary;
  PFND3D12DDI_DESTROY_PIPELINE_LIBRARY_0010                        pfnDestroyPipelineLibrary;
  PFND3D12DDI_ADD_PIPELINE_STATE_TO_LIBRARY_0010                   pfnAddPipelineStateToLibrary;
  PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010                    pfnCalcSerializedLibrarySize;
  PFND3D12DDI_SERIALIZE_LIBRARY_0010                               pfnSerializeLibrary;
} D3D12DDI_DEVICE_FUNCS_CORE_0010;
````


## -struct-fields




#### - pfnCheckFormatSupport

A function that checks format support.


#### - pfnCheckMultisampleQualityLevels

A function that checks multi-sample quality levels. 


#### - pfnGetMipPacking

A function that gets MIP packing.


#### - pfnCalcPrivateElementLayoutSize

A function that calculates layout size for a private element. 


#### - pfnCreateElementLayout

A function that creates an element layout. 


#### - pfnDestroyElementLayout

A function that destroys an element layout.


#### - pfnCalcPrivateBlendStateSize

A function that calculates the size of a private blend state.


#### - pfnCreateBlendState

A function that creates a blend state.


#### - pfnDestroyBlendState

A function that destroys a blend state.


#### - pfnCalcPrivateDepthStencilStateSize

A function that calculates the size of the state of a private depth stencil. 


#### - pfnCreateDepthStencilState

A function that creates a depth stencil state.


#### - pfnDestroyDepthStencilState

A function that destroys a depth stencil state.


#### - pfnCalcPrivateRasterizerStateSize

A function that calculates the size of a private rasterizer state. 


#### - pfnCreateRasterizerState

A function that creates a rasterizer state.


#### - pfnDestroyRasterizerState

A function that destroys a rasterizer state.


#### - pfnCalcPrivateShaderSize

A function that calculates the size of a private shader. 


#### - pfnCreateVertexShader

A function that creates a vertex shader. 


#### - pfnCreatePixelShader

A function that creates a shader.


#### - pfnCreateGeometryShader

A function that creates a geometry shader.


#### - pfnCreateComputeShader

A function that creates a compute shader. 


#### - pfnCalcPrivateGeometryShaderWithStreamOutput

A function that calculates a private geometry shader with stream output. 


#### - pfnCreateGeometryShaderWithStreamOutput

A function that creates a private geometry shader with stream output. 


#### - pfnCalcPrivateTessellationShaderSize

A function that creates private tessellation shader size. 


#### - pfnCreateHullShader

A function that creates a hull shader.


#### - pfnCreateDomainShader

A function that creates a domain shader.


#### - pfnDestroyShader

A function that destroys a shader.


#### - pfnCalcPrivateCommandQueueSize

A function that calculates the size of a private queue.


#### - pfnCreateCommandQueue

A function that creates a command queue.


#### - pfnDestroyCommandQueue

A function that destroys a command queue.


#### - pfnCalcPrivateCommandAllocatorSize

A function that calculates the size of a private command allocator.


#### - pfnCreateCommandAllocator

A function that creates a command allocator.


#### - pfnDestroyCommandAllocator

A function that destroys a command allocator. 


#### - pfnResetCommandAllocator

A function that resets a command allocator. 


#### - pfnCalcPrivatePipelineStateSize

A function that calculate the size of a private pipeline state.


#### - pfnCreatePipelineState

A function that crates a pipeline state.


#### - pfnDestroyPipelineState

A function that destroys a pipeline state.


#### - pfnCalcPrivateCommandListSize

A function that calculate the size of a private command list.


#### - pfnCreateCommandList

A function that creates a command list.


#### - pfnDestroyCommandList

A function that destroys a command list. 


#### - pfnCalcPrivateFenceSize

A function that calculates a private fence size. 


#### - pfnCreateFence

A function that creates a fence.


#### - pfnDestroyFence

A function that destroys a fence. 


#### - pfnCalcPrivateDescriptorHeapSize

A function that calculates the size of a private descriptor heap.


#### - pfnCreateDescriptorHeap

A function that creates a descriptor heap.


#### - pfnDestroyDescriptorHeap

A function that destroys a descriptor heap. 


#### - pfnGetDescriptorSizeInBytes

A function that gets the descriptor size, in bytes.


#### - pfnGetCPUDescriptorHandleForHeapStart

A function that gets a CPU descriptor handle. 


#### - pfnGetGPUDescriptorHandleForHeapStart

A function that gets a GPU descriptor handle.


#### - pfnCreateShaderResourceView

A function that creates a shader resource view. 


#### - pfnCreateConstantBufferView

A function that creates a constant buffer view. 


#### - pfnCreateSampler

A function that creates a sampler.


#### - pfnCreateUnorderedAccessView

A function that creates an unordered access view. 


#### - pfnCreateRenderTargetView

A function that creates a render target view. 


#### - pfnCreateDepthStencilView

A function that creates a depth stencil view. 


#### - pfnCalcPrivateRootSignatureSize

A function that calculates the size of a private root signature. 


#### - pfnCreateRootSignature

A function that creates a root signature. 


#### - pfnDestroyRootSignature

A function that destroys a root signature. 


#### - pfnMapHeap

A function that maps a heap.


#### - pfnUnmapHeap

A function that unmaps a heap.


#### - pfnCalcPrivateHeapAndResourceSizes

A function that calculates sizes for private heap and resource. 


#### - pfnCreateHeapAndResource

A function that create a heap and resource. 


#### - pfnDestroyHeapAndResource

A function that destroys a heap and resource. 


#### - pfnMakeResident

A function that makes a resident. 


#### - pfnEvict

A function that evicts. 


#### - pfnCalcPrivateOpenedHeapAndResourceSizes

A function that calculates sizes for private opened heap and resources. 


#### - pfnOpenHeapAndResource

A function that opens a heap and resource. 


#### - pfnCopyDescriptors

A function that copies descriptors. 


#### - pfnCopyDescriptorsSimple

A function that does a simple copy of descriptors. 


#### - pfnCalcPrivateQueryHeapSize

A function that calculates the size of a private query heap.


#### - pfnCreateQueryHeap

A function that creates a query heap.


#### - pfnDestroyQueryHeap

A function that destroys a query heap. 


#### - pfnCalcPrivateCommandSignatureSize

A function that calculates the size of a private command signature. 


#### - pfnCreateCommandSignature

A function that creates a command signature. 


#### - pfnDestroyCommandSignature

A function that destroys a command signature. 


#### - pfnCheckResourceVirtualAddress

A function that checks the virtual address of a resource.


#### - pfnCheckResourceAllocationInfo

A function that checks allocation information of a resource.


#### - pfnCheckSubresourceInfo

A function that checks information of a subresource. 


#### - pfnCheckExistingResourceAllocationInfo

A function that checks allocation information of an existing resource.


#### - pfnOfferResources

A function that offers resources.


#### - pfnReclaimResources

A function that reclaims resources. 


#### - pfnGetImplicitPhysicalAdapterMask

A function that gets an implicit physical adapter mask.


#### - pfnGetPresentPrivateDriverDataSize

A function that gets the present size of private driver data. 


#### - pfnQueryNodeMap

A function that queries a node map.


#### - pfnRetrieveShaderComment

A function that retrieves a shader comment. 


#### - pfnCheckResourceAllocationHandle

A function that checks a resource allocation handle. 


#### - pfnCalcPrivatePipelineLibrarySize

A function that calculates the size of a private pipeline library.


#### - pfnCreatePipelineLibrary

A function that creates a pipeline library.


#### - pfnDestroyPipelineLibrary

A function that destroys a pipeline library.


#### - pfnAddPipelineStateToLibrary

A function that adds pipeline state to a library.


#### - pfnCalcSerializedLibrarySize

A function that calculates the size of a serialized library.


#### - pfnSerializeLibrary

A function that serializes a library. 


## -see-also

<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_device_funcs_video_0021.md">D3D12DDI_DEVICE_FUNCS_VIDEO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_DEVICE_FUNCS_CORE_0010 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

