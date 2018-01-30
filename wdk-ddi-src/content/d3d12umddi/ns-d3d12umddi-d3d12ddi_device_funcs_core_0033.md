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
ms.keywords: D3D12DDI_DEVICE_FUNCS_CORE_0033 structure [Display Devices], D3D12DDI_DEVICE_FUNCS_CORE_0033, d3d12umddi/D3D12DDI_DEVICE_FUNCS_CORE_0033, display.d3d12ddi-device-funcs-core-0033
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


### -field pfnCalcPrivateCommandAllocatorSize

Calculate private command allocator size.


### -field pfnCreateCommandAllocator

Create command allocator.


### -field pfnDestroyCommandAllocator

Destroy command allocator.


### -field pfnResetCommandAllocator

Reset command allocator.


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

check subresource info.


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

