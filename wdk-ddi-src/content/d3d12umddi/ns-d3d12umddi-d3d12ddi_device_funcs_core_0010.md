---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_CORE_0010
title: D3D12DDI_DEVICE_FUNCS_CORE_0010
author: windows-driver-content
description: Contains core functions.
old-location: display\d3d12ddi_device_funcs_core_0010.htm
old-project: display
ms.assetid: 87B4873E-DD44-47E9-8E6A-5BA91218188F
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D12DDI_DEVICE_FUNCS_CORE_0010, D3D12DDI_DEVICE_FUNCS_CORE_0010 structure [Display Devices], d3d12umddi/D3D12DDI_DEVICE_FUNCS_CORE_0010, display.d3d12ddi_device_funcs_core_0010
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDI_DEVICE_FUNCS_CORE_0010
product: Windows
targetos: Windows
req.typenames: D3D12DDI_DEVICE_FUNCS_CORE_0010
---

# D3D12DDI_DEVICE_FUNCS_CORE_0010 structure


## -description


Contains core functions.


## -struct-fields




### -field pfnCheckFormatSupport

A function that checks format support.


### -field pfnCheckMultisampleQualityLevels

A function that checks multi-sample quality levels. 


### -field pfnGetMipPacking

A function that gets MIP packing.


### -field pfnCalcPrivateElementLayoutSize

A function that calculates layout size for a private element. 


### -field pfnCreateElementLayout

A function that creates an element layout. 


### -field pfnDestroyElementLayout

A function that destroys an element layout.


### -field pfnCalcPrivateBlendStateSize

A function that calculates the size of a private blend state.


### -field pfnCreateBlendState

A function that creates a blend state.


### -field pfnDestroyBlendState

A function that destroys a blend state.


### -field pfnCalcPrivateDepthStencilStateSize

A function that calculates the size of the state of a private depth stencil. 


### -field pfnCreateDepthStencilState

A function that creates a depth stencil state.


### -field pfnDestroyDepthStencilState

A function that destroys a depth stencil state.


### -field pfnCalcPrivateRasterizerStateSize

A function that calculates the size of a private rasterizer state. 


### -field pfnCreateRasterizerState

A function that creates a rasterizer state.


### -field pfnDestroyRasterizerState

A function that destroys a rasterizer state.


### -field pfnCalcPrivateShaderSize

A function that calculates the size of a private shader. 


### -field pfnCreateVertexShader

A function that creates a vertex shader. 


### -field pfnCreatePixelShader

A function that creates a shader.


### -field pfnCreateGeometryShader

A function that creates a geometry shader.


### -field pfnCreateComputeShader

A function that creates a compute shader. 


### -field pfnCalcPrivateGeometryShaderWithStreamOutput

A function that calculates a private geometry shader with stream output. 


### -field pfnCreateGeometryShaderWithStreamOutput

A function that creates a private geometry shader with stream output. 


### -field pfnCalcPrivateTessellationShaderSize

A function that creates private tessellation shader size. 


### -field pfnCreateHullShader

A function that creates a hull shader.


### -field pfnCreateDomainShader

A function that creates a domain shader.


### -field pfnDestroyShader

A function that destroys a shader.


### -field pfnCalcPrivateCommandQueueSize

A function that calculates the size of a private queue.


### -field pfnCreateCommandQueue

A function that creates a command queue.


### -field pfnDestroyCommandQueue

A function that destroys a command queue.


### -field pfnCalcPrivateCommandAllocatorSize

A function that calculates the size of a private command allocator.


### -field pfnCreateCommandAllocator

A function that creates a command allocator.


### -field pfnDestroyCommandAllocator

A function that destroys a command allocator. 


### -field pfnResetCommandAllocator

A function that resets a command allocator. 


### -field pfnCalcPrivatePipelineStateSize

A function that calculate the size of a private pipeline state.


### -field pfnCreatePipelineState

A function that crates a pipeline state.


### -field pfnDestroyPipelineState

A function that destroys a pipeline state.


### -field pfnCalcPrivateCommandListSize

A function that calculate the size of a private command list.


### -field pfnCreateCommandList

A function that creates a command list.


### -field pfnDestroyCommandList

A function that destroys a command list. 


### -field pfnCalcPrivateFenceSize

A function that calculates a private fence size. 


### -field pfnCreateFence

A function that creates a fence.


### -field pfnDestroyFence

A function that destroys a fence. 


### -field pfnCalcPrivateDescriptorHeapSize

A function that calculates the size of a private descriptor heap.


### -field pfnCreateDescriptorHeap

A function that creates a descriptor heap.


### -field pfnDestroyDescriptorHeap

A function that destroys a descriptor heap. 


### -field pfnGetDescriptorSizeInBytes

A function that gets the descriptor size, in bytes.


### -field pfnGetCPUDescriptorHandleForHeapStart

A function that gets a CPU descriptor handle. 


### -field pfnGetGPUDescriptorHandleForHeapStart

A function that gets a GPU descriptor handle.


### -field pfnCreateShaderResourceView

A function that creates a shader resource view. 


### -field pfnCreateConstantBufferView

A function that creates a constant buffer view. 


### -field pfnCreateSampler

A function that creates a sampler.


### -field pfnCreateUnorderedAccessView

A function that creates an unordered access view. 


### -field pfnCreateRenderTargetView

A function that creates a render target view. 


### -field pfnCreateDepthStencilView

A function that creates a depth stencil view. 


### -field pfnCalcPrivateRootSignatureSize

A function that calculates the size of a private root signature. 


### -field pfnCreateRootSignature

A function that creates a root signature. 


### -field pfnDestroyRootSignature

A function that destroys a root signature. 


### -field pfnMapHeap

A function that maps a heap.


### -field pfnUnmapHeap

A function that unmaps a heap.


### -field pfnCalcPrivateHeapAndResourceSizes

A function that calculates sizes for private heap and resource. 


### -field pfnCreateHeapAndResource

A function that create a heap and resource. 


### -field pfnDestroyHeapAndResource

A function that destroys a heap and resource. 


### -field pfnMakeResident

A function that makes a resident. 


### -field pfnEvict

A function that evicts. 


### -field pfnCalcPrivateOpenedHeapAndResourceSizes

A function that calculates sizes for private opened heap and resources. 


### -field pfnOpenHeapAndResource

A function that opens a heap and resource. 


### -field pfnCopyDescriptors

A function that copies descriptors. 


### -field pfnCopyDescriptorsSimple

A function that does a simple copy of descriptors. 


### -field pfnCalcPrivateQueryHeapSize

A function that calculates the size of a private query heap.


### -field pfnCreateQueryHeap

A function that creates a query heap.


### -field pfnDestroyQueryHeap

A function that destroys a query heap. 


### -field pfnCalcPrivateCommandSignatureSize

A function that calculates the size of a private command signature. 


### -field pfnCreateCommandSignature

A function that creates a command signature. 


### -field pfnDestroyCommandSignature

A function that destroys a command signature. 


### -field pfnCheckResourceVirtualAddress

A function that checks the virtual address of a resource.


### -field pfnCheckResourceAllocationInfo

A function that checks allocation information of a resource.


### -field pfnCheckSubresourceInfo

A function that checks information of a subresource. 


### -field pfnCheckExistingResourceAllocationInfo

A function that checks allocation information of an existing resource.


### -field pfnOfferResources

A function that offers resources.


### -field pfnReclaimResources

A function that reclaims resources. 


### -field pfnGetImplicitPhysicalAdapterMask

A function that gets an implicit physical adapter mask.


### -field pfnGetPresentPrivateDriverDataSize

A function that gets the present size of private driver data. 


### -field pfnQueryNodeMap

A function that queries a node map.


### -field pfnRetrieveShaderComment

A function that retrieves a shader comment. 


### -field pfnCheckResourceAllocationHandle

A function that checks a resource allocation handle. 


### -field pfnCalcPrivatePipelineLibrarySize

A function that calculates the size of a private pipeline library.


### -field pfnCreatePipelineLibrary

A function that creates a pipeline library.


### -field pfnDestroyPipelineLibrary

A function that destroys a pipeline library.


### -field pfnAddPipelineStateToLibrary

A function that adds pipeline state to a library.


### -field pfnCalcSerializedLibrarySize

A function that calculates the size of a serialized library.


### -field pfnSerializeLibrary

A function that serializes a library. 


## -see-also




<a href="https://msdn.microsoft.com/F4C385C8-00A2-44AB-A7E6-4C9AA19CFFB0">D3D12DDI_DEVICE_FUNCS_VIDEO</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_DEVICE_FUNCS_CORE_0010 structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

