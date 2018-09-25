---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_CORE_0033
title: D3D12DDI_DEVICE_FUNCS_CORE_0033
author: windows-driver-content
description: Core device functions.
old-location: display\d3d12ddi-device-funcs-core-0033.htm
ms.assetid: c771f360-3641-4e3e-9536-86b31af97932
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3D12DDI_DEVICE_FUNCS_CORE_0033, D3D12DDI_DEVICE_FUNCS_CORE_0033 structure [Display Devices], d3d12umddi/D3D12DDI_DEVICE_FUNCS_CORE_0033, display.d3d12ddi-device-funcs-core-0033
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d12umddi.h
api_name:
-	D3D12DDI_DEVICE_FUNCS_CORE_0033
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_DEVICE_FUNCS_CORE_0033
---

# D3D12DDI_DEVICE_FUNCS_CORE_0033 structure


## -description


Core device functions.


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

