---
UID: NS:d3d10umddi.D3DWDDM2_2DDI_DEVICEFUNCS
title: D3DWDDM2_2DDI_DEVICEFUNCS (d3d10umddi.h)
description: Specifies the callback functions that operate on a shader cache.
old-location: display\d3dwddm2_2ddi_devicefuncs.htm
ms.assetid: 4E082193-70BA-4F36-9001-2A12014F3AC3
ms.date: 05/10/2018
keywords: ["D3DWDDM2_2DDI_DEVICEFUNCS structure"]
ms.keywords: D3DWDDM2_2DDI_DEVICEFUNCS, D3DWDDM2_2DDI_DEVICEFUNCS structure [Display Devices], d3d10umddi/D3DWDDM2_2DDI_DEVICEFUNCS, display.d3dwddm2_2ddi_devicefuncs
f1_keywords:
 - "d3d10umddi/D3DWDDM2_2DDI_DEVICEFUNCS"
req.header: d3d10umddi.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3DWDDM2_2DDI_DEVICEFUNCS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DWDDM2_2DDI_DEVICEFUNCS
---

# D3DWDDM2_2DDI_DEVICEFUNCS structure


## -description


Specifies the callback functions that operate on a shader cache. 


## -struct-fields




### -field pfnDefaultConstantBufferUpdateSubresourceUP

 


### -field pfnVsSetConstantBuffers

 


### -field pfnPsSetShaderResources

 


### -field pfnPsSetShader

 


### -field pfnPsSetSamplers

 


### -field pfnVsSetShader

 


### -field pfnDrawIndexed

 


### -field pfnDraw

 


### -field pfnDynamicIABufferMapNoOverwrite

 


### -field pfnDynamicIABufferUnmap

 


### -field pfnDynamicConstantBufferMapDiscard

 


### -field pfnDynamicIABufferMapDiscard

 


### -field pfnDynamicConstantBufferUnmap

 


### -field pfnPsSetConstantBuffers

 


### -field pfnIaSetInputLayout

 


### -field pfnIaSetVertexBuffers

 


### -field pfnIaSetIndexBuffer

 


### -field pfnDrawIndexedInstanced

 


### -field pfnDrawInstanced

 


### -field pfnDynamicResourceMapDiscard

 


### -field pfnDynamicResourceUnmap

 


### -field pfnGsSetConstantBuffers

 


### -field pfnGsSetShader

 


### -field pfnIaSetTopology

 


### -field pfnStagingResourceMap

 


### -field pfnStagingResourceUnmap

 


### -field pfnVsSetShaderResources

 


### -field pfnVsSetSamplers

 


### -field pfnGsSetShaderResources

 


### -field pfnGsSetSamplers

 


### -field pfnSetRenderTargets

 


### -field pfnShaderResourceViewReadAfterWriteHazard

 


### -field pfnResourceReadAfterWriteHazard

 


### -field pfnSetBlendState

 


### -field pfnSetDepthStencilState

 


### -field pfnSetRasterizerState

 


### -field pfnQueryEnd

 


### -field pfnQueryBegin

 


### -field pfnResourceCopyRegion

 


### -field pfnResourceUpdateSubresourceUP

 


### -field pfnSoSetTargets

 


### -field pfnDrawAuto

 


### -field pfnSetViewports

 


### -field pfnSetScissorRects

 


### -field pfnClearRenderTargetView

 


### -field pfnClearDepthStencilView

 


### -field pfnSetPredication

 


### -field pfnQueryGetData

 


### -field pfnFlush

 


### -field pfnGenMips

 


### -field pfnResourceCopy

 


### -field pfnResourceResolveSubresource

 


### -field pfnResourceMap

 


### -field pfnResourceUnmap

 


### -field pfnResourceIsStagingBusy

 


### -field pfnRelocateDeviceFuncs

 


### -field pfnCalcPrivateResourceSize

 


### -field pfnCalcPrivateOpenedResourceSize

 


### -field pfnCreateResource

 


### -field pfnOpenResource

 


### -field pfnDestroyResource

 


### -field pfnCalcPrivateShaderResourceViewSize

 


### -field pfnCreateShaderResourceView

 


### -field pfnDestroyShaderResourceView

 


### -field pfnCalcPrivateRenderTargetViewSize

 


### -field pfnCreateRenderTargetView

 


### -field pfnDestroyRenderTargetView

 


### -field pfnCalcPrivateDepthStencilViewSize

 


### -field pfnCreateDepthStencilView

 


### -field pfnDestroyDepthStencilView

 


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

 


### -field pfnCreateGeometryShader

 


### -field pfnCreatePixelShader

 


### -field pfnCalcPrivateGeometryShaderWithStreamOutput

 


### -field pfnCreateGeometryShaderWithStreamOutput

 


### -field pfnDestroyShader

 


### -field pfnCalcPrivateSamplerSize

 


### -field pfnCreateSampler

 


### -field pfnDestroySampler

 


### -field pfnCalcPrivateQuerySize

 


### -field pfnCreateQuery

 


### -field pfnDestroyQuery

 


### -field pfnCheckFormatSupport

 


### -field pfnCheckMultisampleQualityLevels

 


### -field pfnCheckCounterInfo

 


### -field pfnCheckCounter

 


### -field pfnDestroyDevice

 


### -field pfnSetTextFilterSize

 


### -field pfnResourceConvert

 


### -field pfnResourceConvertRegion

 


### -field pfnResetPrimitiveID

 


### -field pfnSetVertexPipelineOutput

 


### -field pfnDrawIndexedInstancedIndirect

 


### -field pfnDrawInstancedIndirect

 


### -field pfnCommandListExecute

 


### -field pfnHsSetShaderResources

 


### -field pfnHsSetShader

 


### -field pfnHsSetSamplers

 


### -field pfnHsSetConstantBuffers

 


### -field pfnDsSetShaderResources

 


### -field pfnDsSetShader

 


### -field pfnDsSetSamplers

 


### -field pfnDsSetConstantBuffers

 


### -field pfnCreateHullShader

 


### -field pfnCreateDomainShader

 


### -field pfnCheckDeferredContextHandleSizes

 


### -field pfnCalcDeferredContextHandleSize

 


### -field pfnCalcPrivateDeferredContextSize

 


### -field pfnCreateDeferredContext

 


### -field pfnAbandonCommandList

 


### -field pfnCalcPrivateCommandListSize

 


### -field pfnCreateCommandList

 


### -field pfnDestroyCommandList

 


### -field pfnCalcPrivateTessellationShaderSize

 


### -field pfnPsSetShaderWithIfaces

 


### -field pfnVsSetShaderWithIfaces

 


### -field pfnGsSetShaderWithIfaces

 


### -field pfnHsSetShaderWithIfaces

 


### -field pfnDsSetShaderWithIfaces

 


### -field pfnCsSetShaderWithIfaces

 


### -field pfnCreateComputeShader

 


### -field pfnCsSetShader

 


### -field pfnCsSetShaderResources

 


### -field pfnCsSetSamplers

 


### -field pfnCsSetConstantBuffers

 


### -field pfnCalcPrivateUnorderedAccessViewSize

 


### -field pfnCreateUnorderedAccessView

 


### -field pfnDestroyUnorderedAccessView

 


### -field pfnClearUnorderedAccessViewUint

 


### -field pfnClearUnorderedAccessViewFloat

 


### -field pfnCsSetUnorderedAccessViews

 


### -field pfnDispatch

 


### -field pfnDispatchIndirect

 


### -field pfnSetResourceMinLOD

 


### -field pfnCopyStructureCount

 


### -field pfnRecycleCommandList

 


### -field pfnRecycleCreateCommandList

 


### -field pfnRecycleCreateDeferredContext

 


### -field pfnRecycleDestroyCommandList

 


### -field pfnDiscard

 


### -field pfnAssignDebugBinary

 


### -field pfnDynamicConstantBufferMapNoOverwrite

 


### -field pfnCheckDirectFlipSupport

 


### -field pfnClearView

 


### -field pfnUpdateTileMappings

 


### -field pfnCopyTileMappings

 


### -field pfnCopyTiles

 


### -field pfnUpdateTiles

 


### -field pfnTiledResourceBarrier

 


### -field pfnGetMipPacking

 


### -field pfnResizeTilePool

 


### -field pfnSetMarker

 


### -field pfnSetMarkerMode

 


### -field pfnSetHardwareProtection

 


### -field pfnGetResourceLayout

 


### -field pfnRetrieveShaderComment

 


### -field pfnSetHardwareProtectionState

 


### -field pfnAcquireResource

 


### -field pfnReleaseResource

 


### -field pfnCalcPrivateShaderCacheSessionSize

A callback function that returns the size of a private shader cache session.


### -field pfnCreateShaderCacheSession

A callback function that creates a shader cache session.


### -field pfnDestroyShaderCacheSession

A callback function that destroys a shader cache session.


### -field pfnSetShaderCacheSession

A callback function that sets a shader cache session.

