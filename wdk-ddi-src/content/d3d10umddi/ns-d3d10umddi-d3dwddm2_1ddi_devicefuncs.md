---
UID: NS:d3d10umddi.D3DWDDM2_1DDI_DEVICEFUNCS
tech.root: display
title: D3DWDDM2_1DDI_DEVICEFUNCS
ms.date: 07/29/2022
targetos: Windows
description: Learn more about the D3DWDDM2_1DDI_DEVICEFUNCS structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d10umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WDDM 2.1
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DWDDM2_1DDI_DEVICEFUNCS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3DWDDM2_1DDI_DEVICEFUNCS
f1_keywords:
 - D3DWDDM2_1DDI_DEVICEFUNCS
 - d3d10umddi/D3DWDDM2_1DDI_DEVICEFUNCS
dev_langs:
 - c++
helpviewer_keywords:
 - D3DWDDM2_1DDI_DEVICEFUNCS
---

## -description

This structure contains the user mode device function table for Windows Display Driver Model (WDDM) 2.1. In general, unless a function is commented as optional in *d3d10umdd.h* (or optional under certain conditions), a driver must implement it.

## -struct-fields

### -field pfnDefaultConstantBufferUpdateSubresourceUP

A pointer to the [**DefaultConstantBufferUpdateSubresourceUP**](nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup.md) function.

### -field pfnVsSetConstantBuffers

A pointer to the [**VsSetConstantBuffers**](nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers.md) function.

### -field pfnPsSetShaderResources

A pointer to the [**PsSetShaderResources**](nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md) function.

### -field pfnPsSetShader

A pointer to the [**PsSetShader**](nc-d3d10umddi-pfnd3d10ddi_setshader.md) function.

### -field pfnPsSetSamplers

A pointer to the [**PsSetSamplers**](nc-d3d10umddi-pfnd3d10ddi_setsamplers.md) function.

### -field pfnVsSetShader

A pointer to the [**VsSetShader**](nc-d3d10umddi-pfnd3d10ddi_setshader.md) function.

### -field pfnDrawIndexed

A pointer to the [**DrawIndexed**](nc-d3d10umddi-pfnd3d10ddi_drawindexed.md) function.

### -field pfnDraw

A pointer to the [**Draw**](nc-d3d10umddi-pfnd3d10ddi_draw.md) function.

### -field pfnDynamicIABufferMapNoOverwrite

### -field pfnDynamicIABufferUnmap

### -field pfnDynamicConstantBufferMapDiscard

### -field pfnDynamicIABufferMapDiscard

### -field pfnDynamicConstantBufferUnmap

### -field pfnPsSetConstantBuffers

A pointer to the [**PsSetConstantBuffers**](nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers.md) function.

### -field pfnIaSetInputLayout

A pointer to the [**IaSetInputLayout**](nc-d3d10umddi-pfnd3d10ddi_setinputlayout.md) function.

### -field pfnIaSetVertexBuffers

A pointer to the [**IaSetVertexBuffers**](nc-d3d10umddi-pfnd3d10ddi_ia_setvertexbuffers.md) function.

### -field pfnIaSetIndexBuffer

A pointer to the [**IaSetIndexBuffer**](nc-d3d10umddi-pfnd3d10ddi_ia_setindexbuffer.md) function.

### -field pfnDrawIndexedInstanced

A pointer to the [**DrawIndexedInstanced**](nc-d3d10umddi-pfnd3d10ddi_drawindexedinstanced.md) function.

### -field pfnDrawInstanced

A pointer to the [**DrawInstanced**](nc-d3d10umddi-pfnd3d10ddi_drawinstanced.md) function.

### -field pfnDynamicResourceMapDiscard

### -field pfnDynamicResourceUnmap

### -field pfnGsSetConstantBuffers

A pointer to the [**GsSetConstantBuffers**](nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers.md) function.

### -field pfnGsSetShader

A pointer to the [**GsSetShader**](nc-d3d10umddi-pfnd3d10ddi_setshader.md) function.

### -field pfnIaSetTopology

A pointer to the [**IaSetTopology**](nc-d3d10umddi-pfnd3d10ddi_ia_settopology.md) function.

### -field pfnStagingResourceMap

### -field pfnStagingResourceUnmap

### -field pfnVsSetShaderResources

A pointer to the [**VsSetShaderResources**](nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md) function.

### -field pfnVsSetSamplers

A pointer to the [**VsSetSamplers**](nc-d3d10umddi-pfnd3d10ddi_setsamplers.md) function.

### -field pfnGsSetShaderResources

A pointer to the [**GsSetShaderResources**](nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md) function.

### -field pfnGsSetSamplers

A pointer to the [**GsSetSamplers**](nc-d3d10umddi-pfnd3d10ddi_setsamplers.md) function.

### -field pfnSetRenderTargets

A pointer to the [**SetRenderTargets**](nc-d3d10umddi-pfnd3d10ddi_setrendertargets.md) function.

### -field pfnShaderResourceViewReadAfterWriteHazard

A pointer to the [**ShaderResourceViewReadAfterWriteHazard**](nc-d3d10umddi-pfnd3d10ddi_shaderresourceviewreadafterwritehazard.md) function.

### -field pfnResourceReadAfterWriteHazard

A pointer to the [**ResourceReadAfterWriteHazard**](nc-d3d10umddi-pfnd3d10ddi_resourcereadafterwritehazard.md) function.

### -field pfnSetBlendState

A pointer to the [**SetBlendState**](nc-d3d10umddi-pfnd3d10ddi_setblendstate.md) function.

### -field pfnSetDepthStencilState

A pointer to the [**SetDepthStencilState**](nc-d3d10umddi-pfnd3d10ddi_setdepthstencilstate.md) function.

### -field pfnSetRasterizerState

A pointer to the [**SetRasterizerState**](nc-d3d10umddi-pfnd3d10ddi_setrasterizerstate.md) function.

### -field pfnQueryEnd

A pointer to the [**QueryEnd**](nc-d3d10umddi-pfnd3d10ddi_queryend.md) function.

### -field pfnQueryBegin

A pointer to the [**QueryBegin**](nc-d3d10umddi-pfnd3d10ddi_querybegin.md) function.

### -field pfnResourceCopyRegion

A pointer to the [**ResourceCopyRegion**](nc-d3d10umddi-pfnd3d10ddi_resourcecopyregion.md) function.

### -field pfnResourceUpdateSubresourceUP

A pointer to the [**ResourceUpdateSubresourceUP**](nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup.md) function.

### -field pfnSoSetTargets

A pointer to the [**SoSetTargets**](nc-d3d10umddi-pfnd3d10ddi_so_settargets.md) function.

### -field pfnDrawAuto

A pointer to the [**DrawAuto**](nc-d3d10umddi-pfnd3d10ddi_drawauto.md) function.

### -field pfnSetViewports

A pointer to the [**SetViewports**](nc-d3d10umddi-pfnd3d10ddi_setviewports.md) function.

### -field pfnSetScissorRects

A pointer to the [**SetScissorRects**](nc-d3d10umddi-pfnd3d10ddi_setscissorrects.md) function.

### -field pfnClearRenderTargetView

A pointer to the [**ClearRenderTargetView**](nc-d3d10umddi-pfnd3d10ddi_clearrendertargetview.md) function.

### -field pfnClearDepthStencilView

A pointer to the [**ClearDepthStencilView**](nc-d3d10umddi-pfnd3d10ddi_cleardepthstencilview.md) function.

### -field pfnSetPredication

A pointer to the [**SetPredication**](nc-d3d10umddi-pfnd3d10ddi_setpredication.md) function.

### -field pfnQueryGetData

A pointer to the [**QueryGetData**](nc-d3d10umddi-pfnd3d10ddi_querygetdata.md) function.

### -field pfnFlush

A pointer to the [**Flush**](../wudfddi/nf-wudfddi-iwdfworkitem-flush.md) function.

### -field pfnGenMips

A pointer to the [**GenMips**](nc-d3d10umddi-pfnd3d10ddi_genmips.md) function.

### -field pfnResourceCopy

A pointer to the [**ResourceCopy**](nc-d3d10umddi-pfnd3d10ddi_resourcecopy.md) function.

### -field pfnResourceResolveSubresource

A pointer to the [**ResourceResolveSubresource**](nc-d3d10umddi-pfnd3d10ddi_resourceresolvesubresource.md) function.

### -field pfnResourceMap

A pointer to the [**ResourceMap**](nc-d3d10umddi-pfnd3d10ddi_resourcemap.md) function.

### -field pfnResourceUnmap

A pointer to the [**ResourceUnmap**](nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md) function.

### -field pfnResourceIsStagingBusy

A pointer to the [**ResourceIsStagingBusy**](nc-d3d10umddi-pfnd3d10ddi_resourceisstagingbusy.md) function.

### -field pfnRelocateDeviceFuncs

A pointer to the [**RelocateDeviceFuncs**](nc-d3d10umddi-pfnd3d10ddi_relocatedevicefuncs.md) function.

### -field pfnCalcPrivateResourceSize

A pointer to the [**CalcPrivateResourceSize**](nc-d3d10umddi-pfnd3d10ddi_calcprivateresourcesize.md) function.

### -field pfnCalcPrivateOpenedResourceSize

A pointer to the [**CalcPrivateOpenedResourceSize**](nc-d3d10umddi-pfnd3d10ddi_calcprivateopenedresourcesize.md) function.

### -field pfnCreateResource

A pointer to the [**CreateResource**](../d3dumddi/nc-d3dumddi-pfnd3dddi_createresource.md) function.

### -field pfnOpenResource

A pointer to the [**OpenResource**](../d3dumddi/nc-d3dumddi-pfnd3dddi_openresource.md) function.

### -field pfnDestroyResource

A pointer to the [**DestroyResource**](../d3dumddi/nc-d3dumddi-pfnd3dddi_destroyresource.md) function.

### -field pfnCalcPrivateShaderResourceViewSize

A pointer to the [**CalcPrivateShaderResourceViewSize**](nc-d3d10umddi-pfnd3d10ddi_calcprivateshaderresourceviewsize.md) function.

### -field pfnCreateShaderResourceView

A pointer to the [**CreateShaderResourceView**](nc-d3d10umddi-pfnd3d10ddi_createshaderresourceview.md) function.

### -field pfnDestroyShaderResourceView

A pointer to the [**DestroyShaderResourceView**](nc-d3d10umddi-pfnd3d10ddi_destroyshaderresourceview.md) function.

### -field pfnCalcPrivateRenderTargetViewSize

A pointer to the [**CalcPrivateRenderTargetViewSize**](nc-d3d10umddi-pfnd3d10ddi_calcprivaterendertargetviewsize.md) function.

### -field pfnCreateRenderTargetView

A pointer to the [**CreateRenderTargetView**](nc-d3d10umddi-pfnd3d10ddi_createrendertargetview.md) function.

### -field pfnDestroyRenderTargetView

A pointer to the [**DestroyRenderTargetView**](nc-d3d10umddi-pfnd3d10ddi_destroyrendertargetview.md) function.

### -field pfnCalcPrivateDepthStencilViewSize

A pointer to the [**CalcPrivateDepthStencilViewSize**](nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilviewsize.md) function.

### -field pfnCreateDepthStencilView

A pointer to the [**CreateDepthStencilView**](nc-d3d10umddi-pfnd3d10ddi_createdepthstencilview.md) function.

### -field pfnDestroyDepthStencilView

A pointer to the [**DestroyDepthStencilView**](nc-d3d10umddi-pfnd3d10ddi_destroydepthstencilview.md) function.

### -field pfnCalcPrivateElementLayoutSize

A pointer to the [**CalcPrivateElementLayoutSize**](nc-d3d10umddi-pfnd3d10ddi_calcprivateelementlayoutsize.md) function.

### -field pfnCreateElementLayout

A pointer to the [**CreateElementLayout**](nc-d3d10umddi-pfnd3d10ddi_createelementlayout.md) function.

### -field pfnDestroyElementLayout

A pointer to the [**DestroyElementLayout**](nc-d3d10umddi-pfnd3d10ddi_destroyelementlayout.md) function.

### -field pfnCalcPrivateBlendStateSize

A pointer to the [**CalcPrivateBlendStateSize**](nc-d3d10umddi-pfnd3d10ddi_calcprivateblendstatesize.md) function.

### -field pfnCreateBlendState

A pointer to the [**CreateBlendState**](nc-d3d10umddi-pfnd3d10ddi_createblendstate.md) function.

### -field pfnDestroyBlendState

A pointer to the [**DestroyBlendState**](nc-d3d10umddi-pfnd3d10ddi_destroyblendstate.md) function.

### -field pfnCalcPrivateDepthStencilStateSize

A pointer to the [**CalcPrivateDepthStencilStateSize**](nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilstatesize.md) function.

### -field pfnCreateDepthStencilState

A pointer to the [**CreateDepthStencilState**](nc-d3d10umddi-pfnd3d10ddi_createdepthstencilstate.md) function.

### -field pfnDestroyDepthStencilState

A pointer to the [**DestroyDepthStencilState**](nc-d3d10umddi-pfnd3d10ddi_destroydepthstencilstate.md) function.

### -field pfnCalcPrivateRasterizerStateSize

A pointer to the [**CalcPrivateRasterizerStateSize**](nc-d3d10umddi-pfnd3d10ddi_calcprivaterasterizerstatesize.md) function.

### -field pfnCreateRasterizerState

A pointer to the [**CreateRasterizerState**](nc-d3d10umddi-pfnd3d10ddi_createrasterizerstate.md) function.

### -field pfnDestroyRasterizerState

A pointer to the [**DestroyRasterizerState**](nc-d3d10umddi-pfnd3d10ddi_destroyrasterizerstate.md) function.

### -field pfnCalcPrivateShaderSize

A pointer to the [**CalcPrivateShaderSize**](nc-d3d10umddi-pfnd3d10ddi_calcprivateshadersize.md) function.

### -field pfnCreateVertexShader

A pointer to the [**CreateVertexShader**](nc-d3d10umddi-pfnd3d11_1ddi_createvertexshader.md) function.

### -field pfnCreateGeometryShader

A pointer to the [**CreateGeometryShader**](nc-d3d10umddi-pfnd3d10ddi_creategeometryshader.md) function.

### -field pfnCreatePixelShader

A pointer to the [**CreatePixelShader**](../d3dumddi/nc-d3dumddi-pfnd3dddi_createpixelshader.md) function.

### -field pfnCalcPrivateGeometryShaderWithStreamOutput

A pointer to the [**CalcPrivateGeometryShaderWithStreamOutput**](nc-d3d10umddi-pfnd3d10ddi_calcprivategeometryshaderwithstreamoutput.md) function.

### -field pfnCreateGeometryShaderWithStreamOutput

A pointer to the [**CreateGeometryShaderWithStreamOutput**](nc-d3d10umddi-pfnd3d10ddi_creategeometryshaderwithstreamoutput.md) function.

### -field pfnDestroyShader

A pointer to the [**DestroyShader**](nc-d3d10umddi-pfnd3d10ddi_destroyshader.md) function.

### -field pfnCalcPrivateSamplerSize

A pointer to the [**CalcPrivateSamplerSize**](nc-d3d10umddi-pfnd3d10ddi_calcprivatesamplersize.md) function.

### -field pfnCreateSampler

A pointer to the [**CreateSampler**](nc-d3d10umddi-pfnd3d10ddi_createsampler.md) function.

### -field pfnDestroySampler

A pointer to the [**DestroySampler**](nc-d3d10umddi-pfnd3d10ddi_destroysampler.md) function.

### -field pfnCalcPrivateQuerySize

A pointer to the [**CalcPrivateQuerySize**](nc-d3d10umddi-pfnd3d10ddi_calcprivatequerysize.md) function.

### -field pfnCreateQuery

A pointer to the [**CreateQuery**](../d3dumddi/nc-d3dumddi-pfnd3dddi_createquery.md) function.

### -field pfnDestroyQuery

A pointer to the [**DestroyQuery**](../d3dumddi/nc-d3dumddi-pfnd3dddi_destroyquery.md) function.

### -field pfnCheckFormatSupport

A pointer to the [**CheckFormatSupport**](nc-d3d10umddi-pfnd3d10ddi_checkformatsupport.md) function.

### -field pfnCheckMultisampleQualityLevels

A pointer to the [**CheckMultisampleQualityLevels**](nc-d3d10umddi-pfnd3d10ddi_checkmultisamplequalitylevels.md) function.

### -field pfnCheckCounterInfo

A pointer to the [**CheckCounterInfo**](nc-d3d10umddi-pfnd3d10ddi_checkcounterinfo.md) function.

### -field pfnCheckCounter

A pointer to the [**CheckCounter**](nc-d3d10umddi-pfnd3d10ddi_checkcounter.md) function.

### -field pfnDestroyDevice

A pointer to the [**DestroyDevice**](../d3dumddi/nc-d3dumddi-pfnd3dddi_destroydevice.md) function.

### -field pfnSetTextFilterSize

A pointer to the [**SetTextFilterSize**](nc-d3d10umddi-pfnd3d10ddi_settextfiltersize.md) function.

### -field pfnResourceConvert

### -field pfnResourceConvertRegion

### -field pfnResetPrimitiveID

### -field pfnSetVertexPipelineOutput

### -field pfnDrawIndexedInstancedIndirect

A pointer to the [**DrawIndexedInstancedIndirect**](nc-d3d10umddi-pfnd3d11ddi_drawindexedinstancedindirect.md) function.

### -field pfnDrawInstancedIndirect

A pointer to the [**DrawInstancedIndirect**](nc-d3d10umddi-pfnd3d11ddi_drawinstancedindirect.md) function.

### -field pfnCommandListExecute

A pointer to the [**CommandListExecute**](nc-d3d10umddi-pfnd3d11ddi_commandlistexecute.md) function.

### -field pfnHsSetShaderResources

A pointer to the [**HsSetShaderResources**](nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md) function.

### -field pfnHsSetShader

A pointer to the [**HsSetShader**](nc-d3d10umddi-pfnd3d10ddi_setshader.md) function.

### -field pfnHsSetSamplers

A pointer to the [**HsSetSamplers**](nc-d3d10umddi-pfnd3d10ddi_setsamplers.md) function.

### -field pfnHsSetConstantBuffers

A pointer to the [**HsSetConstantBuffers**](nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers.md) function.

### -field pfnDsSetShaderResources

A pointer to the [**DsSetShaderResources**](nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md) function.

### -field pfnDsSetShader

A pointer to the [**DsSetShader**](nc-d3d10umddi-pfnd3d10ddi_setshader.md) function.

### -field pfnDsSetSamplers

A pointer to the [**DsSetSamplers**](nc-d3d10umddi-pfnd3d10ddi_setsamplers.md) function.

### -field pfnDsSetConstantBuffers

A pointer to the [**DsSetConstantBuffers**](nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers.md) function.

### -field pfnCreateHullShader

A pointer to the [**CreateHullShader**](nc-d3d10umddi-pfnd3d11ddi_createhullshader.md) function.

### -field pfnCreateDomainShader

A pointer to the [**CreateDomainShader**](nc-d3d10umddi-pfnd3d11ddi_createdomainshader.md) function.

### -field pfnCheckDeferredContextHandleSizes

A pointer to the [**CheckDeferredContextHandleSizes**](nc-d3d10umddi-pfnd3d11ddi_checkdeferredcontexthandlesizes.md) function.

### -field pfnCalcDeferredContextHandleSize

A pointer to the [**CalcDeferredContextHandleSize**](nc-d3d10umddi-pfnd3d11ddi_calcdeferredcontexthandlesize.md) function.

### -field pfnCalcPrivateDeferredContextSize

A pointer to the [**CalcPrivateDeferredContextSize**](nc-d3d10umddi-pfnd3d11ddi_calcprivatedeferredcontextsize.md) function.

### -field pfnCreateDeferredContext

A pointer to the [**CreateDeferredContext**](nc-d3d10umddi-pfnd3d11ddi_createdeferredcontext.md) function.

### -field pfnAbandonCommandList

A pointer to the [**AbandonCommandList**](nc-d3d10umddi-pfnd3d11ddi_abandoncommandlist.md) function.

### -field pfnCalcPrivateCommandListSize

A pointer to the [**CalcPrivateCommandListSize**](nc-d3d10umddi-pfnd3d11ddi_calcprivatecommandlistsize.md) function.

### -field pfnCreateCommandList

A pointer to the [**CreateCommandList**](nc-d3d10umddi-pfnd3d11ddi_createcommandlist.md) function.

### -field pfnDestroyCommandList

A pointer to the [**DestroyCommandList**](nc-d3d10umddi-pfnd3d11ddi_destroycommandlist.md) function.

### -field pfnCalcPrivateTessellationShaderSize

A pointer to the [**CalcPrivateTessellationShaderSize**](nc-d3d10umddi-pfnd3d11ddi_calcprivatetessellationshadersize.md) function.

### -field pfnPsSetShaderWithIfaces

A pointer to the [**PsSetShaderWithIfaces**](nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md) function.

### -field pfnVsSetShaderWithIfaces

A pointer to the [**VsSetShaderWithIfaces**](nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md) function.

### -field pfnGsSetShaderWithIfaces

A pointer to the [**GsSetShaderWithIfaces**](nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md) function.

### -field pfnHsSetShaderWithIfaces

A pointer to the [**HsSetShaderWithIfaces**](nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md) function.

### -field pfnDsSetShaderWithIfaces

A pointer to the [**DsSetShaderWithIfaces**](nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md) function.

### -field pfnCsSetShaderWithIfaces

A pointer to the [**CsSetShaderWithIfaces**](nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md) function.

### -field pfnCreateComputeShader

A pointer to the [**CreateComputeShader**](nc-d3d10umddi-pfnd3d11ddi_createcomputeshader.md) function.

### -field pfnCsSetShader

A pointer to the [**CsSetShader**](nc-d3d10umddi-pfnd3d10ddi_setshader.md) function.

### -field pfnCsSetShaderResources

A pointer to the [**CsSetShaderResources**](nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md) function.

### -field pfnCsSetSamplers

A pointer to the [**CsSetSamplers**](nc-d3d10umddi-pfnd3d10ddi_setsamplers.md) function.

### -field pfnCsSetConstantBuffers

A pointer to the [**CsSetConstantBuffers**](nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers.md) function.

### -field pfnCalcPrivateUnorderedAccessViewSize

A pointer to the [**CalcPrivateUnorderedAccessViewSize**](nc-d3d10umddi-pfnd3d11ddi_calcprivateunorderedaccessviewsize.md) function.

### -field pfnCreateUnorderedAccessView

A pointer to the [**CreateUnorderedAccessView**](nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview.md) function.

### -field pfnDestroyUnorderedAccessView

A pointer to the [**DestroyUnorderedAccessView**](nc-d3d10umddi-pfnd3d11ddi_destroyunorderedaccessview.md) function.

### -field pfnClearUnorderedAccessViewUint

A pointer to the [**ClearUnorderedAccessViewUint**](nc-d3d10umddi-pfnd3d11ddi_clearunorderedaccessviewuint.md) function.

### -field pfnClearUnorderedAccessViewFloat

A pointer to the [**ClearUnorderedAccessViewFloat**](nc-d3d10umddi-pfnd3d11ddi_clearunorderedaccessviewfloat.md) function.

### -field pfnCsSetUnorderedAccessViews

A pointer to the [**CsSetUnorderedAccessViews**](nc-d3d10umddi-pfnd3d11ddi_setunorderedaccessviews.md) function.

### -field pfnDispatch

A pointer to the [**Dispatch**](nc-d3d10umddi-pfnd3d11ddi_dispatch.md) function.

### -field pfnDispatchIndirect

A pointer to the [**DispatchIndirect**](nc-d3d10umddi-pfnd3d11ddi_dispatchindirect.md) function.

### -field pfnSetResourceMinLOD

A pointer to the [**SetResourceMinLOD**](nc-d3d10umddi-pfnd3d11ddi_setresourceminlod.md) function.

### -field pfnCopyStructureCount

A pointer to the [**CopyStructureCount**](nc-d3d10umddi-pfnd3d11ddi_copystructurecount.md) function.

### -field pfnRecycleCommandList

A pointer to the [**RecycleCommandList**](nc-d3d10umddi-pfnd3d11ddi_recyclecommandlist.md) function.

### -field pfnRecycleCreateCommandList

A pointer to the [**RecycleCreateCommandList**](nc-d3d10umddi-pfnd3d11ddi_recyclecreatecommandlist.md) function.

### -field pfnRecycleCreateDeferredContext

A pointer to the [**RecycleCreateDeferredContext**](nc-d3d10umddi-pfnd3d11ddi_recyclecreatedeferredcontext.md) function.

### -field pfnRecycleDestroyCommandList

### -field pfnDiscard

A pointer to the [**Discard**](../d3dumddi/nc-d3dumddi-pfnd3dddi_discard.md) function.

### -field pfnAssignDebugBinary

A pointer to the [**AssignDebugBinary**](nc-d3d10umddi-pfnd3d11_1ddi_assigndebugbinary.md) function.

### -field pfnDynamicConstantBufferMapNoOverwrite

### -field pfnCheckDirectFlipSupport

A pointer to the [**CheckDirectFlipSupport**](../d3dumddi/nc-d3dumddi-pfnd3dddi_checkdirectflipsupport.md) function.

### -field pfnClearView

A pointer to the [**ClearView**](nc-d3d10umddi-pfnd3d11_1ddi_clearview.md) function.

### -field pfnUpdateTileMappings

A pointer to the [**UpdateTileMappings**](nc-d3d10umddi-pfnd3dwddm1_3ddi_updatetilemappings.md) function.

### -field pfnCopyTileMappings

A pointer to the [**CopyTileMappings**](nc-d3d10umddi-pfnd3dwddm1_3ddi_copytilemappings.md) function.

### -field pfnCopyTiles

A pointer to the [**CopyTiles**](nc-d3d10umddi-pfnd3dwddm1_3ddi_copytiles.md) function.

### -field pfnUpdateTiles

A pointer to the [**UpdateTiles**](nc-d3d10umddi-pfnd3dwddm1_3ddi_updatetiles.md) function.

### -field pfnTiledResourceBarrier

A pointer to the [**TiledResourceBarrier**](nc-d3d10umddi-pfnd3dwddm1_3ddi_tiledresourcebarrier.md) function.

### -field pfnGetMipPacking

A pointer to the [**GetMipPacking**](nc-d3d10umddi-pfnd3dwddm1_3ddi_getmippacking.md) function.

### -field pfnResizeTilePool

A pointer to the [**ResizeTilePool**](nc-d3d10umddi-pfnd3dwddm1_3ddi_resizetilepool.md) function.

### -field pfnSetMarker

A pointer to the [**SetMarker**](nc-d3d10umddi-pfnd3dwddm1_3ddi_setmarker.md) function.

### -field pfnSetMarkerMode

A pointer to the [**SetMarkerMode**](nc-d3d10umddi-pfnd3dwddm1_3ddi_setmarkermode.md) function.

### -field pfnSetHardwareProtection

Pointer to a [**SetHardwareProtection**](nc-d3d10umddi-pfnd3dwddm2_0ddi_sethardwareprotection.md) function.

### -field pfnGetResourceLayout

### -field pfnRetrieveShaderComment

### -field pfnSetHardwareProtectionState

### -field pfnAcquireResource

### -field pfnReleaseResource
