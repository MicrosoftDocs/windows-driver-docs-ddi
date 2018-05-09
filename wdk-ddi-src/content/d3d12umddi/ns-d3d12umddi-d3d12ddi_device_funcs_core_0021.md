---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_CORE_0021
title: D3D12DDI_DEVICE_FUNCS_CORE_0021
author: windows-driver-content
description: Specifies core device functions.
old-location: display\d3d12ddi_device_funcs_core_0021.htm
old-project: display
ms.assetid: 4E4C3DB3-9C4C-4BBC-82C4-C5C41C0B818C
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3D12DDI_DEVICE_FUNCS_CORE_0021, D3D12DDI_DEVICE_FUNCS_CORE_0021 structure [Display Devices], d3d12umddi/D3D12DDI_DEVICE_FUNCS_CORE_0021, display.d3d12ddi_device_funcs_core_0021
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
-	D3D12DDI_DEVICE_FUNCS_CORE_0021
product:
- Windows
targetos: Windows
req.typenames: D3D12DDI_DEVICE_FUNCS_CORE_0021
---

# D3D12DDI_DEVICE_FUNCS_CORE_0021 structure


## -description


Specifies core device functions. 


## -struct-fields




### -field pfnCheckFormatSupport

 


### -field pfnCheckMultisampleQualityLevels

 


### -field pfnGetMipPacking

 


### -field pfnCalcPrivateElementLayoutSize

 


### -field pfnCreateElementLayout

 


### -field pfnDestroyElementLayout

 


### -field pfnCalcPrivateBlendStateSize

 


### -field pfnCreateBlendState

 


### -field pfnDestroyBlendState

 


### -field pfnCalcPrivateDepthStencilStateSize

 


### -field pfnCreateDepthStencilState

 


### -field pfnDestroyDepthStencilState

 


### -field pfnCalcPrivateRasterizerStateSize

 


### -field pfnCreateRasterizerState

 


### -field pfnDestroyRasterizerState

 


### -field pfnCalcPrivateShaderSize

 


### -field pfnCreateVertexShader

 


### -field pfnCreatePixelShader

 


### -field pfnCreateGeometryShader

 


### -field pfnCreateComputeShader

 


### -field pfnCalcPrivateGeometryShaderWithStreamOutput

 


### -field pfnCreateGeometryShaderWithStreamOutput

 


### -field pfnCalcPrivateTessellationShaderSize

 


### -field pfnCreateHullShader

 


### -field pfnCreateDomainShader

 


### -field pfnDestroyShader

 


### -field pfnCalcPrivateCommandQueueSize

 


### -field pfnCreateCommandQueue

 


### -field pfnDestroyCommandQueue

 


### -field pfnCalcPrivateCommandAllocatorSize

 


### -field pfnCreateCommandAllocator

 


### -field pfnDestroyCommandAllocator

 


### -field pfnResetCommandAllocator

 


### -field pfnCalcPrivatePipelineStateSize

A callback function that calculates the size of a private pipeline state.


### -field pfnCreatePipelineState

A callback function that creates a pipeline state.


### -field pfnDestroyPipelineState

A callback function that destroys  a pipeline state.


### -field pfnCalcPrivateCommandListSize

 


### -field pfnCreateCommandList

 


### -field pfnDestroyCommandList

 


### -field pfnCalcPrivateFenceSize

 


### -field pfnCreateFence

 


### -field pfnDestroyFence

 


### -field pfnCalcPrivateDescriptorHeapSize

 


### -field pfnCreateDescriptorHeap

 


### -field pfnDestroyDescriptorHeap

 


### -field pfnGetDescriptorSizeInBytes

 


### -field pfnGetCPUDescriptorHandleForHeapStart

 


### -field pfnGetGPUDescriptorHandleForHeapStart

 


### -field pfnCreateShaderResourceView

 


### -field pfnCreateConstantBufferView

 


### -field pfnCreateSampler

 


### -field pfnCreateUnorderedAccessView

 


### -field pfnCreateRenderTargetView

 


### -field pfnCreateDepthStencilView

 


### -field pfnCalcPrivateRootSignatureSize

 


### -field pfnCreateRootSignature

 


### -field pfnDestroyRootSignature

 


### -field pfnMapHeap

 


### -field pfnUnmapHeap

 


### -field pfnCalcPrivateHeapAndResourceSizes

 


### -field pfnCreateHeapAndResource

 


### -field pfnDestroyHeapAndResource

 


### -field pfnMakeResident

 


### -field pfnEvict

 


### -field pfnCalcPrivateOpenedHeapAndResourceSizes

 


### -field pfnOpenHeapAndResource

 


### -field pfnCopyDescriptors

 


### -field pfnCopyDescriptorsSimple

 


### -field pfnCalcPrivateQueryHeapSize

 


### -field pfnCreateQueryHeap

 


### -field pfnDestroyQueryHeap

 


### -field pfnCalcPrivateCommandSignatureSize

 


### -field pfnCreateCommandSignature

 


### -field pfnDestroyCommandSignature

 


### -field pfnCheckResourceVirtualAddress

 


### -field pfnCheckResourceAllocationInfo

 


### -field pfnCheckSubresourceInfo

 


### -field pfnCheckExistingResourceAllocationInfo

 


### -field pfnOfferResources

 


### -field pfnReclaimResources

 


### -field pfnGetImplicitPhysicalAdapterMask

 


### -field pfnGetPresentPrivateDriverDataSize

 


### -field pfnQueryNodeMap

 


### -field pfnRetrieveShaderComment

 


### -field pfnCheckResourceAllocationHandle

 


### -field pfnCalcPrivatePipelineLibrarySize

 


### -field pfnCreatePipelineLibrary

 


### -field pfnDestroyPipelineLibrary

 


### -field pfnAddPipelineStateToLibrary

 


### -field pfnCalcSerializedLibrarySize

 


### -field pfnSerializeLibrary

 


### -field pfnGetDebugAllocationInfo

 



