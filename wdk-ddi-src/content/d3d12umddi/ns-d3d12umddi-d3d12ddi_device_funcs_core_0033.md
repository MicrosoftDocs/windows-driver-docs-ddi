---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_CORE_0033
title: D3D12DDI_DEVICE_FUNCS_CORE_0033
author: windows-driver-content
description: Core device functions.
old-location: display\d3d12ddi-device-funcs-core-0033.htm
old-project: display
ms.assetid: c771f360-3641-4e3e-9536-86b31af97932
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_DEVICE_FUNCS_CORE_0033 structure [Display Devices], d3d12umddi/D3D12DDI_DEVICE_FUNCS_CORE_0033, D3D12DDI_DEVICE_FUNCS_CORE_0033, display.d3d12ddi-device-funcs-core-0033
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: 
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
-	d3d12umddi.h
apiname:
-	D3D12DDI_DEVICE_FUNCS_CORE_0033
product: Windows
targetos: Windows
req.typenames: D3D12DDI_DEVICE_FUNCS_CORE_0033
---

# D3D12DDI_DEVICE_FUNCS_CORE_0033 structure


## -description


Core device functions.


## -syntax


````
typedef struct _D3D12DDI_DEVICE_FUNCS_CORE_0033 {
  PFND3D12DDI_CHECKFORMATSUPPORT                                    pfnCheckFormatSupport;
  PFND3D12DDI_CHECKMULTISAMPLEQUALITYLEVELS                         pfnCheckMultisampleQualityLevels;
  PFND3D12DDI_GETMIPPACKING                                         pfnGetMipPacking;
  PFND3D12DDI_CALCPRIVATEELEMENTLAYOUTSIZE_0010                     pfnCalcPrivateElementLayoutSize;
  PFND3D12DDI_CREATEELEMENTLAYOUT_0010                              pfnCreateElementLayout;
  PFND3D12DDI_DESTROYELEMENTLAYOUT                                  pfnDestroyElementLayout;
  PFND3D12DDI_CALCPRIVATEBLENDSTATESIZE_0010                        pfnCalcPrivateBlendStateSize;
  PFND3D12DDI_CREATEBLENDSTATE_0010                                 pfnCreateBlendState;
  PFND3D12DDI_DESTROYBLENDSTATE                                     pfnDestroyBlendState;
  PFND3D12DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE_0025                 pfnCalcPrivateDepthStencilStateSize;
  PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0025                          pfnCreateDepthStencilState;
  PFND3D12DDI_DESTROYDEPTHSTENCILSTATE                              pfnDestroyDepthStencilState;
  PFND3D12DDI_CALCPRIVATERASTERIZERSTATESIZE_0010                   pfnCalcPrivateRasterizerStateSize;
  PFND3D12DDI_CREATERASTERIZERSTATE_0010                            pfnCreateRasterizerState;
  PFND3D12DDI_DESTROYRASTERIZERSTATE                                pfnDestroyRasterizerState;
  PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE_0026                         pfnCalcPrivateShaderSize;
  PFND3D12DDI_CREATE_SHADER_0026                                    pfnCreateVertexShader;
  PFND3D12DDI_CREATE_SHADER_0026                                    pfnCreatePixelShader;
  PFND3D12DDI_CREATE_SHADER_0026                                    pfnCreateGeometryShader;
  PFND3D12DDI_CREATE_SHADER_0026                                    pfnCreateComputeShader;
  PFND3D12DDI_CALC_PRIVATE_GEOMETRY_SHADER_WITH_STREAM_OUTPUT_0026  pfnCalcPrivateGeometryShaderWithStreamOutput;
  PFND3D12DDI_CREATE_GEOMETRY_SHADER_WITH_STREAM_OUTPUT_0026        pfnCreateGeometryShaderWithStreamOutput;
  PFND3D12DDI_CALC_PRIVATE_SHADER_SIZE_0026                         pfnCalcPrivateTessellationShaderSize;
  PFND3D12DDI_CREATE_SHADER_0026                                    pfnCreateHullShader;
  PFND3D12DDI_CREATE_SHADER_0026                                    pfnCreateDomainShader;
  PFND3D12DDI_DESTROYSHADER                                         pfnDestroyShader;
  PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023                      pfnCalcPrivateCommandQueueSize;
  PFND3D12DDI_CREATECOMMANDQUEUE_0023                               pfnCreateCommandQueue;
  PFND3D12DDI_DESTROYCOMMANDQUEUE                                   pfnDestroyCommandQueue;
  PFND3D12DDI_CALCPRIVATECOMMANDALLOCATORSIZE                       pfnCalcPrivateCommandAllocatorSize;
  PFND3D12DDI_CREATECOMMANDALLOCATOR                                pfnCreateCommandAllocator;
  PFND3D12DDI_DESTROYCOMMANDALLOCATOR                               pfnDestroyCommandAllocator;
  PFND3D12DDI_RESETCOMMANDALLOCATOR                                 pfnResetCommandAllocator;
  PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0033                 pfnCalcPrivatePipelineStateSize;
  PFND3D12DDI_CREATE_PIPELINE_STATE_0033                            pfnCreatePipelineState;
  PFND3D12DDI_DESTROY_PIPELINE_STATE                                pfnDestroyPipelineState;
  PFND3D12DDI_CALC_PRIVATE_COMMAND_LIST_SIZE_0001                   pfnCalcPrivateCommandListSize;
  PFND3D12DDI_CREATE_COMMAND_LIST_0001                              pfnCreateCommandList;
  PFND3D12DDI_DESTROYCOMMANDLIST                                    pfnDestroyCommandList;
  PFND3D12DDI_CALCPRIVATEFENCESIZE                                  pfnCalcPrivateFenceSize;
  PFND3D12DDI_CREATEFENCE                                           pfnCreateFence;
  PFND3D12DDI_DESTROYFENCE                                          pfnDestroyFence;
  PFND3D12DDI_CALC_PRIVATE_DESCRIPTOR_HEAP_SIZE_0001                pfnCalcPrivateDescriptorHeapSize;
  PFND3D12DDI_CREATE_DESCRIPTOR_HEAP_0001                           pfnCreateDescriptorHeap;
  PFND3D12DDI_DESTROY_DESCRIPTOR_HEAP                               pfnDestroyDescriptorHeap;
  PFND3D12DDI_GET_DESCRIPTOR_SIZE_IN_BYTES                          pfnGetDescriptorSizeInBytes;
  PFND3D12DDI_GET_CPU_DESCRIPTOR_HANDLE_FOR_HEAP_START              pfnGetCPUDescriptorHandleForHeapStart;
  PFND3D12DDI_GET_GPU_DESCRIPTOR_HANDLE_FOR_HEAP_START              pfnGetGPUDescriptorHandleForHeapStart;
  PFND3D12DDI_CREATE_SHADER_RESOURCE_VIEW_0002                      pfnCreateShaderResourceView;
  PFND3D12DDI_CREATE_CONSTANT_BUFFER_VIEW                           pfnCreateConstantBufferView;
  PFND3D12DDI_CREATE_SAMPLER                                        pfnCreateSampler;
  PFND3D12DDI_CREATE_UNORDERED_ACCESS_VIEW_0002                     pfnCreateUnorderedAccessView;
  PFND3D12DDI_CREATE_RENDER_TARGET_VIEW_0002                        pfnCreateRenderTargetView;
  PFND3D12DDI_CREATE_DEPTH_STENCIL_VIEW                             pfnCreateDepthStencilView;
  PFND3D12DDI_CALC_PRIVATE_ROOT_SIGNATURE_SIZE_0013                 pfnCalcPrivateRootSignatureSize;
  PFND3D12DDI_CREATE_ROOT_SIGNATURE_0013                            pfnCreateRootSignature;
  PFND3D12DDI_DESTROY_ROOT_SIGNATURE                                pfnDestroyRootSignature;
  PFND3D12DDI_MAPHEAP                                               pfnMapHeap;
  PFND3D12DDI_UNMAPHEAP                                             pfnUnmapHeap;
  PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0030                  pfnCalcPrivateHeapAndResourceSizes;
  PFND3D12DDI_CREATEHEAPANDRESOURCE_0030                            pfnCreateHeapAndResource;
  PFND3D12DDI_DESTROYHEAPANDRESOURCE                                pfnDestroyHeapAndResource;
  PFND3D12DDI_MAKERESIDENT_0001                                     pfnMakeResident;
  PFND3D12DDI_EVICT2                                                pfnEvict;
  PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0003            pfnCalcPrivateOpenedHeapAndResourceSizes;
  PFND3D12DDI_OPENHEAPANDRESOURCE_0003                              pfnOpenHeapAndResource;
  PFND3D12DDI_COPY_DESCRIPTORS_0003                                 pfnCopyDescriptors;
  PFND3D12DDI_COPY_DESCRIPTORS_SIMPLE_0003                          pfnCopyDescriptorsSimple;
  PFND3D12DDI_CALC_PRIVATE_QUERY_HEAP_SIZE_0001                     pfnCalcPrivateQueryHeapSize;
  PFND3D12DDI_CREATE_QUERY_HEAP_0001                                pfnCreateQueryHeap;
  PFND3D12DDI_DESTROY_QUERY_HEAP                                    pfnDestroyQueryHeap;
  PFND3D12DDI_CALC_PRIVATE_COMMAND_SIGNATURE_SIZE_0001              pfnCalcPrivateCommandSignatureSize;
  PFND3D12DDI_CREATE_COMMAND_SIGNATURE_0001                         pfnCreateCommandSignature;
  PFND3D12DDI_DESTROY_COMMAND_SIGNATURE                             pfnDestroyCommandSignature;
  PFND3D12DDI_CHECKRESOURCEVIRTUALADDRESS                           pfnCheckResourceVirtualAddress;
  PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0022                      pfnCheckResourceAllocationInfo;
  PFND3D12DDI_CHECKSUBRESOURCEINFO                                  pfnCheckSubresourceInfo;
  PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022             pfnCheckExistingResourceAllocationInfo;
  PFND3D12DDI_OFFERRESOURCES                                        pfnOfferResources;
  PFND3D12DDI_RECLAIMRESOURCES_0001                                 pfnReclaimResources;
  PFND3D12DDI_GETIMPLICITPHYSICALADAPTERMASK                        pfnGetImplicitPhysicalAdapterMask;
  PFND3D12DDI_GET_PRESENT_PRIVATE_DRIVER_DATA_SIZE                  pfnGetPresentPrivateDriverDataSize;
  PFND3D12DDI_QUERY_NODE_MAP                                        pfnQueryNodeMap;
  PFND3D12DDI_RETRIEVE_SHADER_COMMENT_0003                          pfnRetrieveShaderComment;
  PFND3D12DDI_CHECKRESOURCEALLOCATIONHANDLE                         pfnCheckResourceAllocationHandle;
  PFND3D12DDI_CALC_PRIVATE_PIPELINE_LIBRARY_SIZE_0010               pfnCalcPrivatePipelineLibrarySize;
  PFND3D12DDI_CREATE_PIPELINE_LIBRARY_0010                          pfnCreatePipelineLibrary;
  PFND3D12DDI_DESTROY_PIPELINE_LIBRARY_0010                         pfnDestroyPipelineLibrary;
  PFND3D12DDI_ADD_PIPELINE_STATE_TO_LIBRARY_0010                    pfnAddPipelineStateToLibrary;
  PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010                     pfnCalcSerializedLibrarySize;
  PFND3D12DDI_SERIALIZE_LIBRARY_0010                                pfnSerializeLibrary;
  PFND3D12DDI_GET_DEBUG_ALLOCATION_INFO_0014                        pfnGetDebugAllocationInfo;
} D3D12DDI_DEVICE_FUNCS_CORE_0033, D3D12DDI_DEVICE_FUNCS_CORE_0033;
````


## -struct-fields




#### - pfnCheckFormatSupport

Check format support.


#### - pfnCheckMultisampleQualityLevels

Check multi sample quality levels.


#### - pfnGetMipPacking

Get MIP packing.


#### - pfnCalcPrivateElementLayoutSize

Calculate private element layout size.


#### - pfnCreateElementLayout

Create element layout.


#### - pfnDestroyElementLayout

Destroy element layout.


#### - pfnCalcPrivateBlendStateSize

Calculate private blend state size.


#### - pfnCreateBlendState

Create blend state.


#### - pfnDestroyBlendState

Destroy blend state.


#### - pfnCalcPrivateDepthStencilStateSize

Calculate private depth stencil state size.


#### - pfnCreateDepthStencilState

Create depth stencil state.


#### - pfnDestroyDepthStencilState

Destroy depth stencil state.


#### - pfnCalcPrivateRasterizerStateSize

Calculate private rasterizer state size.


#### - pfnCreateRasterizerState

Create rasterizer state.


#### - pfnDestroyRasterizerState

Destroy rasterizer state.


#### - pfnCalcPrivateShaderSize

Calculate private shader size.


#### - pfnCreateVertexShader

Create vertex shader.


#### - pfnCreatePixelShader

Create pixel shader.


#### - pfnCreateGeometryShader

Create geometry shader.


#### - pfnCreateComputeShader

Create compute shader.


#### - pfnCalcPrivateGeometryShaderWithStreamOutput

Calculate private geometry shader with stream output.


#### - pfnCreateGeometryShaderWithStreamOutput

Create geometry shader with stream output.


#### - pfnCalcPrivateTessellationShaderSize

Calculate private tessellation shader size.


#### - pfnCreateHullShader

Create hull shader.


#### - pfnCreateDomainShader

Create domain shader.


#### - pfnDestroyShader

Destroy shader.


#### - pfnCalcPrivateCommandQueueSize

Calculate private command queue size.


#### - pfnCreateCommandQueue

Create command queue.


#### - pfnDestroyCommandQueue

Destroy command queue.


#### - pfnCalcPrivateCommandAllocatorSize

Calculate private command allocator size.


#### - pfnCreateCommandAllocator

Create command allocator.


#### - pfnDestroyCommandAllocator

Destroy command allocator.


#### - pfnResetCommandAllocator

Reset command allocator.


#### - pfnCalcPrivatePipelineStateSize

Calculate private pipeline state size.


#### - pfnCreatePipelineState

Create pipeline state.


#### - pfnDestroyPipelineState

Destroy pipeline state.


#### - pfnCalcPrivateCommandListSize

Calculate private command list size.


#### - pfnCreateCommandList

Create command list.


#### - pfnDestroyCommandList

Destroy command list.


#### - pfnCalcPrivateFenceSize

Calculate private fence size.


#### - pfnCreateFence

Create fence.


#### - pfnDestroyFence

Destroy fence.


#### - pfnCalcPrivateDescriptorHeapSize

Calculate private descriptor heap size.


#### - pfnCreateDescriptorHeap

Create descriptor heap.


#### - pfnDestroyDescriptorHeap

Destroy descriptor heap.


#### - pfnGetDescriptorSizeInBytes

Get descriptor size in bytes.


#### - pfnGetCPUDescriptorHandleForHeapStart

Get CPU descriptor handle for heap start.


#### - pfnGetGPUDescriptorHandleForHeapStart

Get GPU descriptor handle for heap start.


#### - pfnCreateShaderResourceView

Create shader resource view.


#### - pfnCreateConstantBufferView

Create constant buffer view.


#### - pfnCreateSampler

Create sampler.


#### - pfnCreateUnorderedAccessView

Create unordered access view.


#### - pfnCreateRenderTargetView

Create render target view.


#### - pfnCreateDepthStencilView

Create depth stencil view.


#### - pfnCalcPrivateRootSignatureSize

Calculate private root signature size.


#### - pfnCreateRootSignature

Create root signature.


#### - pfnDestroyRootSignature

Destroy root signature.


#### - pfnMapHeap

Map heap.


#### - pfnUnmapHeap

Unmap heap.


#### - pfnCalcPrivateHeapAndResourceSizes

Calculate private heap and resource sizes.


#### - pfnCreateHeapAndResource

Create heap and resource.


#### - pfnDestroyHeapAndResource

Destroy heap and resource.


#### - pfnMakeResident

Make resident.


#### - pfnEvict

Evict.


#### - pfnCalcPrivateOpenedHeapAndResourceSizes

Calculate private opened heap and resource sizes.


#### - pfnOpenHeapAndResource

Open heap and resource.


#### - pfnCopyDescriptors

Copy descriptors.


#### - pfnCopyDescriptorsSimple

Copy descriptors sample.


#### - pfnCalcPrivateQueryHeapSize

Calculate private query heap size.


#### - pfnCreateQueryHeap

Create query heap.


#### - pfnDestroyQueryHeap

Destroy query heap.


#### - pfnCalcPrivateCommandSignatureSize

Calculate private command signature size.


#### - pfnCreateCommandSignature

Create command signature.


#### - pfnDestroyCommandSignature

Destroy command signature.


#### - pfnCheckResourceVirtualAddress

Check resource virtual address.


#### - pfnCheckResourceAllocationInfo

Check resource allocation info.


#### - pfnCheckSubresourceInfo

check subresource info.


#### - pfnCheckExistingResourceAllocationInfo

Check existing resource allocation info.


#### - pfnOfferResources

Offer resources.


#### - pfnReclaimResources

Reclaim resources.


#### - pfnGetImplicitPhysicalAdapterMask

Get implicit physical adapter mask.


#### - pfnGetPresentPrivateDriverDataSize

Get present private driver data size.


#### - pfnQueryNodeMap

Query node map.


#### - pfnRetrieveShaderComment

Retrieve shader comment.


#### - pfnCheckResourceAllocationHandle

Check resource allocation handle.


#### - pfnCalcPrivatePipelineLibrarySize

Calculate private pipeline library size.


#### - pfnCreatePipelineLibrary

Create pipeline library.


#### - pfnDestroyPipelineLibrary

Destroy pipeline library.


#### - pfnAddPipelineStateToLibrary

Add pipeline state to library.


#### - pfnCalcSerializedLibrarySize

Calculate serialized library size.


#### - pfnSerializeLibrary

Serialize library.


#### - pfnGetDebugAllocationInfo

Get debug allocation info.

